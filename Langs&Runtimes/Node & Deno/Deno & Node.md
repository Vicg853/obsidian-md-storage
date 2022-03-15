_**Node and Deno**_

Both are runtimes, that allow many environments (desktop, backend, mobile) to understand and run JS programs. Both are pretty reliable and have each one their own advantages. They are based on Chromium’s V8 engine that runs/compiles JS code. But they have their little differences: Node is older, with a bigger community and has quite an experience on big applications used by companies around the world. Meanwhile, Deno is kinda like a newborn, he is faster, also uses V8 engine, but is coded in Rust and has as main features better security policies and native typescript support. Thanks for Ryan Dahl and it’s team for creating both technologies which are amazing and help so many people around the world

Node: [](https://nodejs.org/en/)[https://nodejs.org/](https://nodejs.org/) Deno: [](https://deno.land/)[https://deno.land/](https://deno.land/)

_**Node (the old and strong brother)**_

_**Deno (the faster and student newborn)**_

> Deno’s own explanation: ”Deno aims to be a productive and secure s*cripting environment for the modern programmer.

Deno will always be distributed as a single executable. Given a URL to a Deno program, it is runnable with nothing more than the ~25 megabyte zipped executable. Deno explicitly takes on the role of both runtime and package manager. It uses a standard browser-compatible protocol for loading modules: URLs.

Among other things, Deno is a great replacement for utility scripts that may have been historically written with Bash or Python.”*

> Deno’s objectives (quote): *”Ship as just a single executable (`deno`).

Provide secure defaults Unless specifically allowed, scripts can't access files, the environment, or the network

Be browser-compatible The subset of Deno programs which are written completely in JavaScript and do not use the global `Deno` namespace (or feature test for it), ought to also be able to be run in a modern web browser without change.

Provide built-in tooling to improve developer experience. E.g. unit testing, code formatting, and linting.

Keep V8 concepts out of user land.

Serve HTTP efficiently.”*

-   Main characteristics
    
    -   Native typescript support
    -   Module global caching and import via remote URL (auto dep management) only as ES Modules
    -   Security policies that requires pre-runtime permission flags (for: Network, Read filesystem, Write filesystem, Env access, Dynamic lib import, High resolution time measurement, Subprocess runtime) (some of them are even customizable to only specified resources)
    -   Single runtime file with only ~25MB
    -   Built in utilities (at the moment are: code formatter, linter, bundler. tester, watcher)
    -   Can bundle all into a single JS file
    -   Native Fetch support
-   DENO’S MAGIC: THE CORE
    
-   Useful CLI snippets and config
    
    ```bash
    > # Shell install"
    > curl -fsSL <https://deno.land/x/install/install.sh> | sh
    
    > # VS Code .vscode/config.json config (requires Deno's VS Code extenssion: <https://marketplace.visualstudio.com/items?itemName=denoland.vscode-deno>)
    > $PROJECT_PATH=~/hello_deno && mkdir $PROJECT_PATH
    > touch $PROJECT_PATH/.vscode/config.json && cd PROJECT_PATH/.vscode/config.json && \\
    echo '{
       "deno.enable": true,
       "deno.lint": true,
       "deno.unstable": false
    }' >> config.json
    
    > # Help command (three options)
    > deno help && deno -h && deno --help
    
    > # Help also works with other commands
    > deno help bundle && deno bundle -h && deno bundle --help
    
    > # Deno bundler
    > deno bundle
    
    > # Deno run and wathc run (respectivelly)
    > deno run {source file} && deno run --watch {source file}
    
    > # !! Keep in mind, that for most commands with source option, all arguments passed after the file source argument
    > # will be cosidered as script argument and will be passed to running script. For deno owns arguments, write
    > # after command and before file source !!
    
    ```
    
    Other snippets:
    
    -   [](https://deno.land/manual@v1.17.1/getting_started/command_line_interface)[https://deno.land/manual@v1.17.1/getting_started/command_line_interface](https://deno.land/manual@v1.17.1/getting_started/command_line_interface)
    
    Config file:
    
    -   [](https://deno.land/manual@v1.17.1/getting_started/configuration_file)[https://deno.land/manual@v1.17.1/getting_started/configuration_file](https://deno.land/manual@v1.17.1/getting_started/configuration_file)
    
    Debugging:
    
    -   [](https://deno.land/manual@v1.17.1/getting_started/debugging_your_code)[https://deno.land/manual@v1.17.1/getting_started/debugging_your_code](https://deno.land/manual@v1.17.1/getting_started/debugging_your_code) Simple snippet for it:
    
    ```bash
    > # For debugging you may use two diferent falgs: --inspect and --inspect-brk
    > # which respectively allow: remote inspector to connect at any time, or
    > # blocks the code execution in the first line until... at least one debugger connect's
    
    > deno run --inspect-brk
    
    > # Then inside chrome for example access: chrome://inspect and you shold be abble
    > # to see an option to inspect deno's instance
    
    ```
    
-   Permissions
    
    _**CLI:**_ [](https://deno.land/manual@v1.17.1/getting_started/permissions)[https://deno.land/manual@v1.17.1/getting_started/permissions](https://deno.land/manual@v1.17.1/getting_started/permissions)
    
    _**Runtime API:**_ (more on [](https://deno.land/manual@v1.17.1/runtime/permission_apis)[https://deno.land/manual@v1.17.1/runtime/permission_apis](https://deno.land/manual@v1.17.1/runtime/permission_apis)) ******Permissions a usually grand on CLI. But this is not guaranteed, so to prevent runtime errors Deno provides an API to request/check/revoke permissions on runtime. On runtime permission management is made in a query format called descriptors. E.g.: `-allow-read=/foo/bar` corresponds to `{ name: "read", path: "/foo/bar" }` There are three methods to keep in mind (all are asynchronous events, as it demands user interactions):
    
    -   _Check/query permission:_ `Deno.permissions.query({ /* Query */)`
    -   _Request permission grant:_ `Deno.permissions.request({ /* Query */)`
    -   _Revoke permission:_ `Deno.permissions.revoke({ /* Query */)`
    
    On queries, permissions names are almost the same as the ones present in the CLI, just remove the`--allow-`. They almost all accept either a specific permission passed via a key or global ones by passing no other key: -**`env`_**for env variables (accepts: global or specific var using “ ” key)**_, -`hrtime`_**for high-precision time (accepts: global)**_, -`ffi`_**for dynamic libraries (accepts: global)**_, -`read`_**for filesystem read (accepts: global or specific path using “path” key)**_, -`run`_**for subprocess invoke (accepts: global or specific subprocess access via “command” key)**_, -`write`_**for filesystem write (accepts: global or specific path using “path” key)**_,
    
    -   `net`** _for filesystem write (accepts: global or specific hosts, ip using “host”, “ip” key (respectively))_**, -`all`**_for all permissions grant (accepts: global)_
    
    And what about permission states. Permission state are returned inside an object by the “key” for every method called in `Deno.permissions`:
    
    -   ”granted” for permissions granted from the API or CLI
    -   “prompt” for permissions that have not been granted but may be requested via `Deno.permissions.request` method
    -   “denied” for permissions that have been explicitly refused when `Deno.permissions.request` was called or via the cli
    
    Something to keep in mind are permissions strength. For example if you grant write permission to “/foo” a path called “/bar” whose parent is “/foo” will be accessible by the app and if “127.0.0.1” is allowed as a network interface, so is “127.0.0.1:8000”. This is important as it may influence in your app’s security.
    
-   APIs
    
    -   Web Platform APIs
        
        Deno implements many APIs that are very alike native Browser APIs. They pretty much follow almost the same rules/specifications as the Chrome and Firefox implementations. Keep them in mind, try using them before thinking of reinventing the wheel
        
        -   _**Fetch API:**_ fetch API can be used to make HTTP requests
            
            (as specified in: [](https://fetch.spec.whatwg.org/)[https://fetch.spec.whatwg.org/](https://fetch.spec.whatwg.org/)) Deviations from the original fetch api:
            
            -   Deno does not process or filters set-cookie header
            -   Deno does not follow same-origin policy (does not follow whatwg: 3.1, 3.2, 3.5, 3.6, “Atomic HTTP redirect handling” and “The `opaqueredirect` response type“ sections
            -   Fetch with manual redirect will return an basic response instead of an opaque redirect one
            -   Specification about fetching local files: [](https://deno.land/manual@v1.17.1/runtime/web_platform_apis#fetching-local-files)[https://deno.land/manual@v1.17.1/runtime/web_platform_apis#fetching-local-files](https://deno.land/manual@v1.17.1/runtime/web_platform_apis#fetching-local-files)
        -   `CustomEvent`, `EnventTarget` and `EventListener` are provided by Deno (follows: [](https://dom.spec.whatwg.org/#events)[https://dom.spec.whatwg.org/#events](https://dom.spec.whatwg.org/#events))
            
        
        ---
        
        -   Blob (fully follows: [](https://developer.mozilla.org/en-US/docs/Web/API/Blob)[https://developer.mozilla.org/en-US/docs/Web/API/Blob](https://developer.mozilla.org/en-US/docs/Web/API/Blob))
        
        ---
        
        -   Broadcast channel (fully follows: [](https://developer.mozilla.org/en-US/docs/Web/API/BroadcastChannel)[https://developer.mozilla.org/en-US/docs/Web/API/BroadcastChannel](https://developer.mozilla.org/en-US/docs/Web/API/BroadcastChannel))
        
        ---
        
        -   Channel Messaging API (fully follows: [](https://developer.mozilla.org/en-US/docs/Web/API/Channel_Messaging_API)[https://developer.mozilla.org/en-US/docs/Web/API/Channel_Messaging_API](https://developer.mozilla.org/en-US/docs/Web/API/Channel_Messaging_API))
        
        ---
        
        -   Console (well, you know what it follows and you wtf this is c’mon)
        
        ---
        
        -   Encoding API (fully follows: [](https://developer.mozilla.org/en-US/docs/Web/API/Encoding_API)[https://developer.mozilla.org/en-US/docs/Web/API/Encoding_API](https://developer.mozilla.org/en-US/docs/Web/API/Encoding_API))
        
        ---
        
        -   Form Data (fully follows: [](https://developer.mozilla.org/en-US/docs/Web/API/FormData)[https://developer.mozilla.org/en-US/docs/Web/API/FormData](https://developer.mozilla.org/en-US/docs/Web/API/FormData))
        
        ---
        
        -   Performance (fully follows: [](https://developer.mozilla.org/en-US/docs/Web/API/Performance)[https://developer.mozilla.org/en-US/docs/Web/API/Performance](https://developer.mozilla.org/en-US/docs/Web/API/Performance))
        
        ---
        
        -   `setTimeout`, `setInterval`, `clearInterval` (fully follows: [](https://developer.mozilla.org/pt-BR/docs/Learn/JavaScript/Asynchronous/Timeouts_and_intervals)[https://developer.mozilla.org/pt-BR/docs/Learn/JavaScript/Asynchronous/Timeouts_and_intervals](https://developer.mozilla.org/pt-BR/docs/Learn/JavaScript/Asynchronous/Timeouts_and_intervals))
        
        ---
        
        -   Data stream (fully follows: [](https://developer.mozilla.org/en-US/docs/Web/API/Streams_API)[https://developer.mozilla.org/en-US/docs/Web/API/Streams_API](https://developer.mozilla.org/en-US/docs/Web/API/Streams_API))
        
        ---
        
        -   URL API (fully follows: [](https://developer.mozilla.org/en-US/docs/Web/API/URL)[https://developer.mozilla.org/en-US/docs/Web/API/URL](https://developer.mozilla.org/en-US/docs/Web/API/URL))
        
        ---
        
        -   URL pattern API (fully follows: [](https://developer.mozilla.org/en-US/docs/Web/API/URLPattern)[https://developer.mozilla.org/en-US/docs/Web/API/URLPattern](https://developer.mozilla.org/en-US/docs/Web/API/URLPattern))
        
        ---
        
        -   URL Search params API (fully follows: [](https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams)[https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams](https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams))
        
        ---
        
        -   Web strg(fully follows: [](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API)[https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API))
        
        ---
        
        -   Web workers (fully follows: [](https://developer.mozilla.org/en-US/docs/Web/API/Worker)[https://developer.mozilla.org/en-US/docs/Web/API/Worker](https://developer.mozilla.org/en-US/docs/Web/API/Worker))
        
        ---
        
        -   Websocket (fully follows: [](https://developer.mozilla.org/en-US/docs/Web/API/WebSocket)[https://developer.mozilla.org/en-US/docs/Web/API/WebSocket](https://developer.mozilla.org/en-US/docs/Web/API/WebSocket))
    
    _**High level HTTP API and Low-level one:**_ Deno’s docs warn that the low-level API can be quite tricky to get things right. The difference between the two of them is that the low-level one is the one directly provided by Deno, while the higher one uses components from de std lib
    
    -   HTTP API
        
        <aside> 💡 Need to import std lib: [](https://deno.land/std@0.119.0/http/server.ts)[https://deno.land/std@0.119.0/http/server.ts](https://deno.land/std@0.119.0/http/server.ts)
        
        </aside>
        
        _**Handling HTTP:**_ for HTTP requests the std lib provides a `server()` function that must receive a handler function as first parameter. As second parameter an option object can be passed to specify `port`, `host` , ... (by default server listens on port 8000). The handler function may be synchronous or asynchronous and will return a `Response` , `ReadableStream`(in case it is an asynchronous handler, it must be defined as `Promise<Response>`)
        
        <aside> 🚨 To keep in mind for readable streams: make sure you handle client hang up, otherwise the handler will keep running until running out of memory and may return errors
        
        </aside>
        
        _**HTTPS:**_ this type of server is as well provided by the std library as the`serveTls()` function. It has two additional parameters: `certFile` and `keyFile` which are strings containing TLS certificates credentials
        
        _**WebSocket:**_ for Websockets the server is the same as the res/req server. The only thing is that inside the handler an server upgrade will occur by using Deno’s built in `Deno.upgradeWebSocket`that will return the a `socket` object and a `response` object. With the socket object will handle, well... anything related with your socket, in the meanwhile the response object must be returned to the server function, as it will handle the upgrade. As Websocket are symmetrical, Deno’s server socket has the same specifications described on MDN [](https://developer.mozilla.org/en-US/docs/Web/API/WebSocket)[https://developer.mozilla.org/en-US/docs/Web/API/WebSocket](https://developer.mozilla.org/en-US/docs/Web/API/WebSocket) Deno is planning on migrating to [](https://github.com/ricea/websocketstream-explainer/blob/master/README.md)[https://github.com/ricea/websocketstream-explainer/blob/master/README.md](https://github.com/ricea/websocketstream-explainer/blob/master/README.md) which provides an easier implementation of Websocket
        
        <aside> ℹ️ Handle WebSocket upgrade error with a normal Response (using try catch)
        
        </aside>
        
        _**Inspecting requests:**_ well you obviously need to get data from the request. All is passed via the `req` parameter passed to the handler by the server.
        
        <aside> 🚨 To keep in mind: you must handle client hang up, as when reading anything from body, server will keep running in this case trying to receive body’s remaining content
        
        </aside>
        
        ```tsx
        //Server example 
        import { serve } from "<https://deno.land/std@0.119.0/http/server.ts>"
        
        serve(handler, { port: 1234 })
        
        //Handler example
        function handler(req: Request): Response {
        
        	//Stream 
          const timer
          const body = new ReadableStream({
            async start(controller) {
              timer = setInterval(() => {
                controller.enqueue("Hello, World!\\n");
              }, 1000)
            },
            },
            cancel() {
              clearInterval(timer)
            },
          })
        
        	//Normal response
          return new Response(body, {
        		status: 200,
            headers: {
              "content-type": "text/plain; charset=utf-8",
            },
          })
        }
        
        //For async handler
        async function handler(req: Request): Promise<Response> { 
        	return new Response('Hello World') 
        }
        
        //Web socket
        function handler(req: Request): Response {
          const upgrade = req.headers.get("upgrade") || "";
          let socket, response;
          try {
            res = Deno.upgradeWebSocket(req);
            socket = res.socket;
            response = res.response;
          } catch {
            return new Response("request isn't trying to upgrade to websocket.");
          }
          socket.onopen = () => console.log("socket opened");
          socket.onmessage = (e) => {
            console.log("socket message:", e.data);
            socket.send(new Date().toString());
          };
          socket.onerror = (e) => console.log("socket errored:", e.message);
          socket.onclose = () => console.log("socket closed");
          return response;
        }
        
        //Req params examples 
        async function handler(req: Request): Promise<Response> {
          console.log("Method:", req.method);
        
          const url = new URL(req.url);
          console.log("Path:", url.pathname);
          console.log("Query parameters:", url.searchParams);
        
          console.log("Headers:", req.headers);
        
          if (req.body) {
            const body = await req.text();
            console.log("Body:", body);
          }
        
          return new Response("Hello, World!");
        }
        
        ```
        
    -   HTTP low-level API
        
        The low-level API is quite similar the high-level one. _**Listening/handling connections:**_ both are handled by `Deno` interface as methods: `Deno.listen()` and `Deno.listenTls()` the two of them have the same behaviour as the higher level APIs. The difference are in, the fact that instead of receiving a handler, they instead return the server instance with handler in a variable and they may receive some adicional properties as options:
        
        ```tsx
        //HTTP server
        const server = Deno.listen({ 
        	port: 8080, //Port to run on
        	transport: "tcp", //speicify the listener protocol will use for conections
        	hostname: "localhost" //specify, well... the hostname to run on
        })
        
        //HTTPS server
        const serverTls = Deno.listenTls({
          port: 8443, //Port
          certFile: "localhost.crt", //Certificate
          keyFile: "localhost.key", //Certficiate token/key
          alpnProtocols: ["h2", "http/1.1"], //Protocols to use (here for example we are using HTTP/2 and HTTP/1.1
        })
        
        //Both return the folowing methods (they are all async)
        for await (const conn of server) {  //**************** server.con
          // ...handle the connection...
        }
        while (true) {
          try {
            const conn = await server.accept() //*************** server.accept()
            // ... handle the connection ...
          } catch (err) {
            // The listener has closed
            break
          }
        }
        
        server.close() //To close the listener
        ```
        
        Exception handling in both cases are quite important, to handle connection errors, especially when using TLS as unknown certificates and etc are quite common.
        
        _**HTTP/2 and other protocols:**_ Deno supports for the moment HTTP/2 and HTTP/1.1 (respectively as “h2”, “http/1.1”). HTTP/2 when activated is usually negotiated at ALPN. To turn on http/2 you must pass it to the property `alpnProtocols` on`Deno.listenTls()` method options, it consist of a string[] that may receive the values described inside the parenthesis of the first sentence. Note: HTTP/2 is only available with a TLS/HTTPS connection as
        
        _**HTTP serving/handling:**_ well, before handling HTTP requests/response we need to serve http connection. For this, Deno provides a build in `serveHttp()` method which receives the connection parameter passed by the listener and that will return an `Deno.HttpConn`object containing http request/response events as well as a `.nextRequest()`method which can be used to await for next request. This method is as well asynchronous and must be handled by an async iterator too.
        
        <aside> ⚠️ Note that you must surround serverHttp with an IIFE as if we awaited for the http connection on the global scope, we could block additional connections to the listener
        
        </aside>
        
        ```tsx
        const server = Deno.listen({ port: 8080 })
        
        while (true) {
          try {
            const conn = await server.accept()
            (async () => {
              const httpConn = Deno.serveHttp(conn)
              while (true) {
                try {
                  const requestEvent = await httpConn.nextRequest()
                  // ... handle requestEvent ...
                } catch (err) {
                  // the connection has finished
                  break
                }
              }
            })()
          } catch (err) {
            // The listener has closed
            break
          }
        }
        ```
        
        As seen, `Deno.HttpConn` will asynchronously provide request/response events, it is the `Deno.RequestEvent` that will contain a `.request` property and a `.respondWith()` method.
        
        ```tsx
        // .request property 
        async function handle(conn: Deno.Conn) {
          const httpConn = Deno.serveHttp(conn);
          for await (const requestEvent of httpConn) {
            const url = new URL(requestEvent.request.url);
            console.log(`path: ${url.pathname}`);
          }
        }
        
        // .respondWith() method
        async function handle(conn: Deno.Conn) {
          const httpConn = Deno.serveHttp(conn);
          for await (const requestEvent of httpConn) {
            await requestEvent.respondWith(
              new Response("hello world", {
                status: 200,
              }),
            );
          }
        }
        ```
        
        _**Websockets:**_ The websocket implementation is done in the same way as the higher-level API, the only diference now, is that the websocket upgrade response will be provided to the `.respondWith()` method from servHttp
        
    -   Location API
        
        As we are not running on a browser, Deno allow a document location emulation by specifying the following using the `—-location` flag. This flag is required or an error will be throw.
        
        API is automatically supported by fetch API and worker modules
        
    -   Storage API
        
        Deno provides a browser like storage API. It has the same methods/properties as in the browser. Differently than session storage that only persist data for the current execution, storage persists from execution to execution. It has a 10MB storage limit.
        
        Deno has some rules to define it’s unique storage location:
        
        -   If a location is provided on the CLI, the origin and origin protocol are used to define an unique storage.
        -   If there is no location but a config file is provided Deno will use the file’s absolute path as origin for the storage.
        -   If there is none, Deno uses the current running file absolute workspace path as origin. It does this by the REPL that creates a synthetic main module from the current working directory. That means for example that multiple REPL invocations from the same path will share the same storage unit
    -   Workers
        
        Deno provides a threaded worker API, so each instance will run in it’s own thread. For the moment Workers can only be modules, so the flag `{ type: “module” }` as options is required. And, to reference the worker’s file you need to reference it using URL. Then you must provide the path source using `—-location` in the CLI or by using `import.meta.url`
        
        ```tsx
        new Worker(new URL("./worker.js", import.meta.url).href, { type: "module" });
        ```
        
        In Deno, Workers are considered like dynamic scripts import, so some permissions must be granted to the Worker creator script:
        
        -   For local scripts: `--allow-read` is required
        -   For remote scripts: `--allow-net` is required
        
        <aside> ⚠️ Initially workers do not contain Deno namespace, so to allow it you must pass as option `{ deno: { namespace: true } }` and to keep in mind, this functionality is unstable so run with `—-unstable`
        
        </aside>
        
        _**Main script and worker communication (requires deno namespace):**_ to communicate between the two interfaces, in the worker invoker, the worker class return a worker interface where you can for example use the `.postMessage()` method to send message to the worker and receive it in the worker via the `.onmessage()` async method, by reading the self variable.
        
        _**Workers permission:**_ you may grant special permissions to the worker thread. If not specified, Worker will by default inherit parent’s process permissions. Some specifications about the permissions:
        
        -   For granular permissions, you may pass an array with each permission (and when using urls, they may be either relative or absolute path, but keep in mind that when using relative, the path will be relative to the worker’s path)
        -   They may receive true and false to simply allow/disallow any permission
        -   When passed “inherit”, to a permission it will inherit the parent’s process permissions
        -   To disable all permissions, instead of passing an object with each permission, just pass “none” to the permissions property
        -   If only one permission is passed, all other permissions will inherit the parent’s process one
        
        ```tsx
        // No permission
        const worker = new Worker(new URL("./worker.js", import.meta.url).href, {
          type: "module",
          deno: {
            namespace: true,
            permissions: "none",
          },
        })
        
        // Inherit all jsut not the net one
        const worker = new Worker(new URL("./worker.js", import.meta.url).href, {
          type: "module",
          deno: {
            namespace: true,
            permissions: {
              net: false,
            },
          },
        })
        
        // All permissions example and an true/false + inherit
        const worker = new Worker(new URL("./worker.js", import.meta.url).href, {
          type: "module",
          deno: {
            namespace: true,
            permissions: {
              env: false,
              hrtime: false,
              net: "inherit",
              ffi: false,
              read: false,
              run: false,
              write: false,
            },
          },
        })
        
        //For granular permissions
        const worker = new Worker(new URL("./worker.js", import.meta.url).href, {
          type: "module",
          deno: {
            namespace: true,
            permissions: {
              net: [
                "<https://deno.land/>",
              ],
              read: [
                new URL("./file_1.txt", import.meta.url),
                new URL("./file_2.txt", import.meta.url),
              ],
              write: false,
            },
          },
        })
        ```
        
    -   Foreign Function Interface API
        
        Deno provides a FFI API, that allows you to call libraries written in native languages that support C ABIs (Rust, C/C++, C#, Zig, Nim, Kotlin, etc)
        
        <aside> ⚠️ Keep in mind that this feature is unstable and must run with `—-unstable` and must be ran with FFI permission: `--allow-ffi`
        
        </aside>
        
        To run it, you must compile the C/Rust/etc code first, and then refer to it in TS as with the file path (it may vary in function of the OS it is running on keep this in mind). To actually open and use you must use `Deno.dlOpen()` method where, as options, you will pass the parameter and methods present that will be used, as well as their specifications (parameters for methods and types for parameters). This will return an object containing the other code features.
        
        Note that, to create parameters and etc types, you must use FFI API types, you can see the list here: [](https://deno.land/manual@v1.17.1/runtime/ffi_api#supported-types)[https://deno.land/manual@v1.17.1/runtime/ffi_api#supported-types](https://deno.land/manual@v1.17.1/runtime/ffi_api#supported-types)
        
        FFI can be referenced as non-blocking functions, that will return a promise. This way, you may run for example CPU-bound FFI without bocking your main thread.
        
        ```tsx
        //Example FFI that adds two numbers
        const libName = `./libadd.so` //Remeber, this extenssion may vary and you need in some cases handle this
        // Open library and define exported symbols
        const dylib = Deno.dlopen(libName, {
          "add": { parameters: ["isize", "isize"], result: "isize" },
        })
        
        // Call the symbol `add`
        const result = dylib.symbols.add(35, 34)
        
        console.log(`Result from external addition of 35 and 34: ${result}`);
        
        //Non-blocking FFI that sleeps for the defined time
        const library = Deno.dlopen("./sleep.so", {
          sleep: {
            parameters: ["usize"],
            result: "void",
            nonblocking: true,
          },
        })
        
        library.symbols.sleep(500).then(() => console.log("After"))
        console.log("Before")
        ```
        
        For Rust, Deno has a Rust specific library in which you can help you generate bindings and import them easier directly into your code: [](https://deno.land/manual@v1.17.1/runtime/ffi_api#deno_bindgen)[https://deno.land/manual@v1.17.1/runtime/ffi_api#deno_bindgen](https://deno.land/manual@v1.17.1/runtime/ffi_api#deno_bindgen)
        
-   Browser compatibility
    
    _**Lifecycle**_ Deno supports `load` and `unload` browser lifecycle events. Load listeners can either be asynchronous and synchronous. Meanwhile unload listeners must be synchronous. Both can not be canceled.
    
    To use them, you can use either `window.addEventListener` and `window.onload`/`window.onunload`... ``...but caution, they have different behaviours. While Deno calls and executes all `window.addEventListener` but in case you multiple `window.onload` or `window.onunload` listeners, only the last one will be executed (even if you use both cases).
    
    ```jsx
    //Example -> 1
    window.addEventListener('onload', () => console.log('Load A') //This will be executed
    window.addEventListener('onload', () => console.log('Load B') //This will be executed
    
    window.addEventListener('unload', () => console.log('Unload A') //This will be executed
    window.addEventListener('unload', () => console.log('Unload B') //This will be executed
    
    //Example -> 2 
    window.onload = () => console.log('Load A') //This will be executed
    window.onload = () => console.log('Load B') //Not executed 
    
    window.onunload = () => console.log('Unload A') //This will be executed
    window.onunload = () => console.log('Unload B') //Not executed
    ```
    
-   Modules
    
    Denos modules are imported with urls. Differently than Node, modules are globally installed and shared between your apps.
    
    To reload a module installations for an app: `deno cache --reload my_module.ts`
    
    To reload specific modules (you may specify multiple ones with comas in between them): `deno cache --reload=https://deno.land/std@0.119.0 my_module.ts`
    
    Deno saves all modules in cache inside your machine and your app will use this cached dependencies until cache is reloaded or it is runed in a different machine. But in this case, it can cause your app to use incorrect dependencies or versions. To prevent this you may compile your code and use the lock flag to save dependencies:
    
    -   To only specify a lock file and enable it: `--lock=lock.json`
    -   To specify and reload a the lock file: `--lock=lock.json --lock-write`
    -   To load dependencies: `deno cache --reload --lock=lock.json src/deps.ts`
    -   For runtime with deps verification: `deno run --lock=lock.json --cached-only mod.ts`
    
    For private module handling: [](https://deno.land/manual@v1.17.1/linking_to_external_code/private)[https://deno.land/manual@v1.17.1/linking_to_external_code/private](https://deno.land/manual@v1.17.1/linking_to_external_code/private)
    
    TS module importing types [](https://deno.land/manual@v1.17.1/typescript/overview#supported-media-types)[https://deno.land/manual@v1.17.1/typescript/overview#supported-media-types](https://deno.land/manual@v1.17.1/typescript/overview#supported-media-types)
    
    _**Configuring typescript in Deno:**_ you can configure typescript in a Deno config file by specifying `—-config` flag at runtime. The avaible configuration is listed here [](https://deno.land/manual@v1.17.1/typescript/configuration#how-deno-uses-a-configuration-file)[https://deno.land/manual@v1.17.1/typescript/configuration#how-deno-uses-a-configuration-file](https://deno.land/manual@v1.17.1/typescript/configuration#how-deno-uses-a-configuration-file) And here are the type libs that are build into Deno and must be specified within custom config: [](https://deno.land/manual@v1.17.1/typescript/configuration#using-the-quotlibquot-property)[https://deno.land/manual@v1.17.1/typescript/configuration#using-the-quotlibquot-property](https://deno.land/manual@v1.17.1/typescript/configuration#using-the-quotlibquot-property)
    
    _**Modules type declarations:**_ to declare typings [](https://deno.land/manual@v1.17.1/typescript/types)[https://deno.land/manual@v1.17.1/typescript/types](https://deno.land/manual@v1.17.1/typescript/types)
    
-   Testing and linting
    
-   Bundling and compiling