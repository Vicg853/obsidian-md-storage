When at least one of a trait's methods are unsafe, a that trait is considered  unsafe too.

So not only itself but also all implementations of it, must be annotated as ``unsafe``.

```rust
struct MyStruct {}

unsafe trait A {
	fn a(x: i32) -> i32;
}

unsafe impl A for MyStruct {}
```