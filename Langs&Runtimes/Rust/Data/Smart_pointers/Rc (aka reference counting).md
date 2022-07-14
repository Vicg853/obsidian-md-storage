The reference counting pointer, is similar to a Rust reference, mixed with a box pointer. But, it differs from them, as it must get ownership of the underlying data and keeps a reference count.

This allows us to store data, reference it at other places and only dropped the respective data when you aren't using it anymore (when all references are dropped). Even better, it actually allows you to own the data, when using the pointer in other places.

> **INFO** Reference counter pointers, only store immutable references and allow immutable access.

## Declaring
The reference counting pointer is defined on Rust's std library
```rust
use std::rc::Rc:

let a = Rc::new("Hello World".to_string());

let b = Rc::clone(&a); //"b" owns "a"'s data
let c = Rc::clone(&a); //"c" owns "a"'s data
```

> Note that, to access the data we use the ``::clone`` method. This method does not actually hard clones a values like similar methods around Rust, it only adds to the reference count and links the variable to the reference counter

## Getting a reference count
To get the current reference count, you may use the ``::strtong_count()`` passing the desired pointer as a reference.
It returns an integer.