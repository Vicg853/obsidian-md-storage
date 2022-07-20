Rust has a great versatility when it comes to interfacing with bare-metal or programs written in other languages, such as C++, C, etc. 

There is usually an only issue with that: applying these methods, means in most cases, that the compiler won't be able to understand some things and ensure memory, runtime, and etc. safety.
Also, in really really complex cases, the compiler may not understand what is happening.

For that, Rust features unsafe methods. When using unsafe, Rust allows us to do some previously forbidden actions and skip some checks and when taking good care of safety yourself, this can be a great resource ("uma mão na roda" as the Portuguese expression).

## Usage
Among other methods, the most straightforward way to write unsafe code, is using the ``unsafe`` keyword followed by brackets, that will create an unsafe code scope.

```rust
unsafe {
	let b = &mut a *const isize;
	let c = &a as *mut isize; 
}
```
