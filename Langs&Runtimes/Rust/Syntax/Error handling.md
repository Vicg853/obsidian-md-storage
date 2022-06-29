There are two standards for error handling in Rust, which are pretty similar to other language's error handling:
- Panicking, which will stop the program's execution;
- And the result Enum. 

## Panic
Panicking, is useful on test, prototypes or when it is inevitable and not applying it could cause some form program of degradation. 

#### the ``panic`` macro
The main way to panic can be done by calling the ``panic!()`` macro:
```rust
if let None == a {
	panic!("Value a does not exist");
}
```

The panic macro can be used alongside the ``RUST_BACKTRACE=1`` environment variable, which make Rust show the program's error trace (more information from where something panicked, when and where was it called, its parent functions, modules and files).

#### Unwarp method
Another way to panic, is to use the ``.unwarp()`` method when it is available. 
It is also useful on cases where you know that something won't error, but still return option or error responses (e.g.: parsing a statically typed str).

```rust
			//Statically type, won't error 
let a = "1234".parse().unwarp();
```

## Result Enum
Preferred for productions cases, is using the Result Enum, which is included by default in the program's scope, because of its frequent usage and forces us to handle it on returns. 

It allows us to handle errors gracefully, without necessarily stopping a program's execution and allow practicing the called "Error propagation" method.

The Result method features a ``Ok`` variant which represents success and a ``Err`` variant which represents error. 

The Result Enum follows this definition: 
```rust
enum Result<T, E> { 
	Ok(T),
	Err(E)
}
```

As you can see, it required two generics, which are the return type and the error return type. 

#### Returning a result
Returning a result is easy: you just use the ``return`` keyword or make your expression the last element on a function. 

```rust
fn returns_err() -> Result<String> {
	if true {
		Ok("Success");
	} else {
		Err("Err 😬!");
	}
}
```

The return subject should be then the ``Err`` variant or the ``Ok`` variant. 

#### Handling the result enum
There are many ways to handle the result enum, that go from methods to using pure syntax. 

Some of them are: 
- _The match expression_: 
	```rust
	fn a() {
		match File::open("hello_world.txt") {
			Ok(file) => file,
			Err(err) => match err.kind() {
				ErrorKind::NotFound => println!("File could not be found!"),
				other => println!("An unknown error occured while openning the file! Trace: {:?}", other)
			}
		}
	}
	```

- _Unwarp or else method + closures_: Another, more readable way to handle this can be done with closures and the ``unwrap_or_else()`` method.
	```rust
	fn b() {
		File::open("hello_world.txt").unwarp_or_else(|err| {
			if err.kind() == ErrorKind::NotFound {
				println!("File could not be found!");
			} else {
				println!("An unknown error occured while openning the file! Trace: {:?}", err);
			}
		})
	}
	```

- _Expect method_: The ``.expect()`` method, is similar to the ``.unwarp()`` method, but does not panic. It will automatically return an error message in case of errors.  
```rust
fn c() {
	File::open("hello_world.txt").expect("Failed openning the file");
}
```

#### The ``?`` operator
The question mark operator, works in a very similar way to the ``.expect()`` method: it will not panic and will return either the underlying error or go on with things.

#### The main fn
There are some limitation when handling ``main`` function level error events. 
The main function does not primarily support this return type, so we must adapt it, for it to handle them: 
```rust
fn main() -> Result<(), Box<dyn Error>> {
	//....
}
```

Here we are defining ``main``'s return type to either nothing, denoted by the empty parenthesis (called unit) or a dynamic error trait object (more about them [here]), which means the error could be of any kind. 