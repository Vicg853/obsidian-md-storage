Rust must at compile type, know type sizes. For example, if we use the ``str`` type without a ``&`` reference, we would get an error. 

So values must usually have a known compile time known size and implement the ``Sized`` trait, or be referenced by any pointer type, which have known sizes at compile time. 

## With generics
Generic types, must have their type know at compile time, just as other types. But sometimes, we might want to pass elements which size is not known.

We can do that, by defining our generic as a type that implements the ``Sized`` trait after a ``?`` point. This only work for this specific trait and tells Rust that the respective generic does not have a compile time known size. 
With that, we also need to define the underlying value as a reference.

```rust
fn my_func<T: ?Sized>(arg: &T) {
	//---
}
```