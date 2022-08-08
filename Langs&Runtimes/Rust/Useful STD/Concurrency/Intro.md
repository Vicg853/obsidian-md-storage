In the Rust book, concurrency is taught under the "Fearless concurrency" title as the language also focus on thread safety, apart from memory safety.

The only catch is, as Rust tries to provide a agnostic as possible runtime, it only features low-level threads (or OS threads, or kernel threads). The std library does not provide the called green-threads (or User level threads, or virtual thread), which can still be implemented and developed by third parties or by yourself.

The Rust model helps you reduce most runtime concurrency errors, down to compile time errors, mitigating production issues.

## Intro
The thread functionality is provided by the ``std`` library under the ``thread`` module.

You can create a new thread using the ``spawn`` function, passing to it a closure. 

```rust
use std::thread;

fn main() {
	thread::spawn(|| {
		println!("Hello world!");
	})
}
```

We can wait for a certain thread to finish, using the ``.join()`` handling method.

```rust 
use std::thread;

fn main() {
	let my_thread = thread::spawn(|| {
		println!("Hello world!");
	});

	my_thread.join().unwrap();
}
```

And as for variable passing, Rust can't ensure that a variable will still be valid when a thread executes, so values from outside a thread, must be moved into it using the ``move`` closure keyword (in cases you are not using other methods as state sharing, message passing, etc).

```rust
fn main() {
	let x = 1;
	
	thread::spawn(move || {
		println!("{}", x);
	})
}
```

## Other methods
Obviously, there is more to see about threads in Rust, that manipulate the current executing thread and creates bridges between multiple threads.

Three big ones are message passing methods, covered [here](./Message_passing), state sharing [here](./State_sharing) and concurrency with the ``Sync`` and ``Send``, covered [here](./Sync_and_Send). 

Here, are some smaller methods:

#### The ``sleep`` func
We may use the ``thread::sleep()`` function, to make the current thread sleep for a certain time-span, passed to this function. It accepts a ``Duration`` struct as argument.