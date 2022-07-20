Foreign function interfaces are considered unsafe code in Rust (at least when importing, but not when exporting). 

When importing external functions we use the special ``extern`` syntax, that creates a scope where we may define external functions, these functions, will be behave in the same way as ``unsafe`` functions.

## Importing
Another element when importing FFIs, is defining the ABI (Application binary interface) that Rust should use for the underlying defined functions, this is done through string containing the ABI's name (e.g.: ``"C"`` for the C programming language ABI)

```rust 
extern "C" {
	fn my_c_func(input: i32) -> i32;
}

unsafe {
	let a = my_c_func(10);
}
```

## Exporting
Exporting FFIs does not necessarily involves unsafe code. But it consist of similar definition and is also usually accompanied by the ``#[no_mangle]`` annotation, so Rust doesn't modify the function's name. 

```rust
#[no_mangle]
pub extern "C" fn call_from_c() { }
```

> Note that similarly to when exporting modules, we must use the ``pub`` keyword at definition.