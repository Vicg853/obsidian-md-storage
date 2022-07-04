When using smart pointers or references, in some cases (e.g.: comparison of two values), we can't simply use the reference variable (e.g.: ``5 == a`` where ``let a = &b;``). 

So that is why the deref operator exists. It is used with _any type_ that _implements_ the _``Deref``_ or _``DerefMut``_ and _makes Rust use the underlying stored data, instead of the actual pointer's value_ (that only consiste of adresses). 

In some cases, the Rust compiler can do it by itself, with no instructions whatsoever. 

When the compiler does this by itself it is called _"Deref coercion"_ and when done by hand it is called _"Implicit Deref coercion"_.

## Usage
The deref operator consist of a simple start placed before any reference or pointer:
```rust
let a = 5;
let my_ref = &a;

assert!(5, *my_ref);
```

## Implementing deref capabilities
We may implement the deref trait to, our own custom smart pointer as an example. For that we need to import the deref trait from the STD library and implement our custom ``deref`` method:
```rust
use std::ops::Deref;

struct MySmartPointer<T>(T);

impl<T> Deref for MySmartPointer<T> {
	fn deref(&self) -> &Self::Target {
		&self.0
	}
}
```

Now our smart pointer can be dereferenced: Rust will convert our ``*val`` to ``*(val.deref())`` by itself and capture the underlying value.

## Deref coercion rules
Deref coercion is applied when we are trying to switch from a type to another, usually in function arguments. On only a couple of cases deref coercion can be applied automatically:
- When transforming an immutable reference into another immutable reference, when the target implements the ``Deref`` trait
- From a mutable reference to an immutable reference, when the target implements the ``DerefMut`` trait
- From a mutable reference to another mutable reference, when the target implements the ``Deref`` trait

> Note that, it can be done from an immutable reference to a mutable reference, as the ownership rules can't assure that there aren't any other immutable references to the same value int the same scope