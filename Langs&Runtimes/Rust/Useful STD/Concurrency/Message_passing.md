Message passing in Rust, is analogous to a river stream, water comes from a source and ends up at the bottom of that stream. This corresponds in Rust, to a sender source, that sends a message which will end up at the receiving thread.

The Rust ``std`` lib provides such functionality with the ``mpsc`` module, located under the ``sync`` module. It provides methods to create message streams between threads. 
The main difference between reality and the previous analogy is that, there can be many send handlers, while there is an only receiver endpoint, which may receive message from all senders, hence the meaning of mpsc: "multiple-producer", "single-consumer". 

When either the only receiver or all senders are dropped, the channel is dropped itself. 

It can be useful for example, when creating a cluster of threads to divide calculations. Each threads sends it result to a main thread, that assembles all results.

## Usage
To create a cross-thread message stream, we use the ``channel()`` function, which returns a tuple with to elements: as transmitter variable and a receiver variable (usually called ``tx`` and ``rx`` respectively). 

We can send a message with the sender variable, using the ``.send()`` method and receive using the blocking ``.recv()`` method. They can communicate any variable type and both return a ``Result`` enum. 

```rust
use std::{
	sync::mpsc,
	thread
};

fn main() {
	let (tx, rx) = mpsc::channel();
	
	thread::spawn(move || {
		let my_message = String::from("Hi from a foreign world!");
		tx.send(my_message).unwrap();
	});

	let received_message = rx.recv().unwwarp();
	println!("{}", received_message);
}
```

> *Note*: thread messaging also follows the ownership model, that is: values are *moved* to the receiver thread, when sent, more specifically, the sender thread, loses ownership over that data.

## Multiple messages
When sending and receiving multiple messages: 
- to send, you can simply call the ``.send()`` method as many times as you will;
- to receive, instead of calling the ``.recv()`` method on the receiver variable, we can treat it as an iterator, calling it in a ``for`` loop. 

```rust
fn main() {
	let (tx, rx) = mpsc::channel(); 

	thread::spawn(move || { 
		let vals = vec![ 
			String::from("My"), 
			String::from("Big"), 
			String::from("Message")
		]; 
		
		for val in vals { 
			tx.send(val).unwrap();
		}
	}); 
	
	for received in rx { 
		println!("Got: {}", received); 
	}
}
```

## Multiple senders
To create multiple senders, we may use the ``.clone()`` method, present under the sender variable.

```rust
fn main() {
	let (tx, rx) = mpsc::channel(); 
	
	let tx1 = tx.clone(); 
	
	thread::spawn(move || { 
		let msg = String::from("Hi from thread 1"); 
		tx.send(msg1).unwrap(); 
	}); 
	
	thread::spawn(move || { 
		let msg1 = String::from("Hi from thread 2"); 
		tx1.send(msg1).unwrap(); 
	}); 
	
	for received in rx { 
		println!("Message received: {}", received); 
	}
}
```