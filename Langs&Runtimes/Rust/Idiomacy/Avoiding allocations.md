Speed can be quite a tricky subject, but still is kind of an essential thing to think about. Rust is fast by nature, but still, we need to be careful as anything that we do, can still affect performance.

Memory allocation, is one of the things that can be quite disruptive in performance matters. Here are some tips to prevent them.

#### Take func
Sometimes, we might need to duplicate or clone data and when this is done, new memory is allocated on the heap, which can increase memory consumption and time complexity.

We may however, prevent it by using rust's ``std::mem``'s ``take`` function. The ``take`` function, instead of creating an additional allocation, will replace the default created memory at declaration, by the underlying value. 

Explained by example:
```rust
use std::mem;

enum User {
	Reader { name: Sring },
	Writer { name: Sring }
}

fn promote(u: &mut User) {
	use User::*;

	*u = match u {
		Reader { name } => Writer { name: mem::take(name) }, //Here, instead of using the .clone() method, we use the take function. It instead of allocating new memory it will override the default string value of the name variable with the previously defined name variable.
		Whirter { name: _ } => return
	}
}
```