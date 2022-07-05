When smart pointers are dropped, their underlying data can't be left hanging on the system. And that is why the drop trait exists.

The drop trait can be implemented to any custom smart pointer and automatically drops any data type when the pointer is dropped and implements the ``.drop()`` method to it. 

## Manual drop
You may also drop the pointer and its value manually, by passing it to the  ``drop()`` function, included by default into the program's scope.

```rust
let a = Box::new(String::from("Hello World!"));

drop(a);
```

It is forbidden to do it in any other way, for example by using the ``.drop()`` method manually.
This could cause Rust to try dropping the underlying value as second time when the pointer goes out of scope, causing in a double free. 