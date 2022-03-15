When we use SSR modules and apps and start mixing server-side code with font-end code, an issue usually appears: what is only supposed to run/be on the server and what's supposed to be on the client ?
This is tricky and can sometimes even lead to big issues, like, sensitive data/logic/info leaking!

We'll, this subject can probably extend to an enormous article with algorithms, three-shaking and other explanations or solutions... 
But here we're going to cover and shorten the good practices provided by [Remix](https://remix.run/docs/en/v1.2.3/guides/constraints) to prevent issues regarding this on remix: 

### Server code pruning on remix
Remix automatically prunes code that isn't supposed to be on client bundles, but you need to take some crucial steps for this:

- Logging, or running functions directly in the file scope, the called: *Module side effect*
```js
	import { prisma } from '../db'

	console.log(prisma);
```
This will cause remix to add this function onto the client's bundle as it will be executed directly on file import and can't be proxied by remix. So only include root scoped code that is supposed to run on the browser

### High order functions
```js
	//File 1

	export function removeTrailingSlash(loader) {
		//...
      return redirect(request.url.slice(0, -1), {
        status: 308,
      });
		//...
		return loader(arg);
	}

	//File 2
	import { removeTrailingSlash } from "file1";

	export const loader = removeTrailingSlash(({ request }) => {
	  return { some: "data" };
	});

```
Like this example given on [remix](https://remix.run/docs/en/v1.2.3/guides/constraints#higher-order-functions) (full example on this link) using higher order function on exports directly do not work and this code will create a side-effect.

So instead of using a push function architecture for an early response like this example, you should use an pull function architecture: 
```js
	//File 1

	export function removeTrailingSlash(url) {
		if (url.pathname.endsWith("/")) {
		   throw redirect(request.url.slice(0, -1), {
			   status: 308,
			});
		}
	}

	//File 2
	import { removeTrailingSlash } from 'file1'

	export const loader = async ({ request }) => {
	  removeTrailingSlash(request.url);
	  return { some: "data" };
	};
```

It also looks nicer when you have multiple abstractions, which can get ugly with push functions and it's callbacks.

### Browser-only code
One thing that should also be noted are client only code... It shouldn't present a vulnerability (although it can), but will probably cause unexpected and 500 errors, as it may try to access client only avaible APIs. 

So in the following cases you should pay a lot of attention to prevent headaches:
- Document guard: 
   When accessing browser only APIs, you should use document guards, to prevent things from running 
   ```js
		//See, it's quite simple, so do it
		if (typeof document !== "undefined")
	```
	(⚠️ notice that we use document variable, you may also use window, but some ssr runtimes may include these APIs on the server, like Deno🦖)
- Lazy initialization: 
  ```js
	  export async function redirectToStripeCheckout(sessionId) {
		  const stripe = await loadStripe(window.ENV.stripe);
		  return stripe.redirectToCheckout({ sessionId });
	  }
  ```
  Along with this, sometimes you may run into multiple lib/framework initialization, sou you may use may use module-scoped variables to prevent this:
  ```js
	  let _lib
	  async function getLib() {
		  if(!_lib) return await loadLib()
		  else return _lib
	  }
  ```
- When practicing render with browser only APIs, things can get tricky... kidding, you can just use React's *``useEffect``* hook on most cases, to fix this. This way, code will be only executed when on the browser and SSR won't cause any problems: 
  (like on this local storage state custom hook):
 ```js
	 function useLocalStorage(key) {
		 const [state, setState] = useState(null);

	    useEffect(() => {
		    setState(localStorage.getItem(key));
	    }, [key]);

	    const setWithLocalStorage = (nextState) => {
		    setState(nextState);
	    };

		 return [state, setWithLocalStorage];
	 }
 ```
- 3rd party modules: 
   Some 3rd parties try to access ``window`` or similar browser APIs... for that, remix recommends finding alternatives, but if can't, they also recommend using [patch-package](https://www.npmjs.com/package/patch-package) to fix this