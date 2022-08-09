In some cases an omnidirectional channel isn't enough and we must share a variable across multiple points. 
When working with threads, sharing a variable isn't that simple, we must account facts like, the data being accessible across various processes, mutability across them, simultaneous variable access, etc.

Thankfully, Rust provides resources to fix those problems, the main one being mutexes, which is also a pretty common paradigm in general comp sci. Mutexes provide shared access to a variable, that can be shared throughout different threads. 

It works with a lock-release system: when accessing a variable, we must acquire its lock, which its can/will only be acquired when no other locks are active. 

In Rust, we must wrap our data inside a mutex and call the ``.lock()`` method to access a reference of it. The ``.lock()`` method, will return a ``MutexGuard`` smart pointer, which implements both the ``Drop`` and ``Deref`` trait. 
Which means, that, to access the underlying mutex data, we must dereference it with ``*`` and when the pointer goes out of scope, both itself and the its respective lock are dropped.

Though, when passing the mutex variable itself onto other threads, the ownership rules must be applied as we've seen with thread cllosures, which means, the mutex smart pointer it not that useful alone. 
So, we need to use something similar to the ``Rc`` (about it the ``Rc`` smrt pntr [here](../../Data/Smart_pointers/Rc_(aka_reference_counting))) smart pointer along with it: the ``Arc``, which stands for "Atomic reference counting". 

The ``Arc`` smrt pntr, differently than its brother ``Rc``, is thread safe (it will be able to keep track of all owners across thread accurately).

### Definition and usage
```rust
use str::{sync::{Mutex, Arc}, thread};

fn main() {
	let counter = Arc::new(Mutex::new(0));
	let first_mut = Arc::clone(&counter);
	let second_mut = Arc::clone(&counter);

	thread::spawn(move || {
		let mut inner_counter = first_mut.lock().unwrap();

		*num += 1;
	});

	println!("Count is of: {}",*counter.lock().unwrap())
}
```

### Risks
Mutexes sadly aren't bullet proof and we must take care when working with them, as they can create the called ___deadlocks___. Deadlocks occur when, by some reason, two threads acquire a lock at the same time, causing them to infinitely keep waiting for each other, to drop the lock. 

Hopefully, there are practices to mitigate this, which can be found online.

Also, we must carefully check, if a lock will be dropped, otherwise, there could be issues with dangling locks blocking every other lock request.
