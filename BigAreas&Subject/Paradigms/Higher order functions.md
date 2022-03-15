### The basic definition: ([source](https://en.wikipedia.org/wiki/Higher-order_function)):
In mathematics and computer science, a higher-order function is a function that does at least one of the following:
- takes one or more functions as arguments ,
- returns a function as its result

### Example (using js)
```js
	function a(bool, callback) {
		if(!!bool){
			callback();
			return;
		} 
		else {
			console.log('Callback not called!');
			return;
		}
	};

	a(true, console.log('Callback called!'));
```
