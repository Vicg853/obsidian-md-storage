## Never type
The never type is pretty commonly used. But it is usually done under the hood, in ``for``, ``loop``, ``while`` loops, or the panic ``panic`` macro, among others. 

It is denoted as an ``!`` point and references a non-return type. For example if a function possibly ``panics`` at some point in its execution, it means that it may return nothing in the end.

The compiler usually figures things out by itself, when the function may return either a never or an existing type, and definition is not explicitly required.

```rust 
fn my_func() -> ! {
	panic!("AAAAHH!!")
}
```