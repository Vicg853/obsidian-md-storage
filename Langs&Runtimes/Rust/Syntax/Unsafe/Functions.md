We may also declare unsafe functions. Unsafe functions, create an unsafe scope inside them and can than only be called inside unsafe scope. 

Note that unsafe functions, must be carefully used and you must pay attention to its arguments, as not respecting them could cause undefined behaviour. 

## Definition
```rust 
unsafe fn dangerous() {}
```

## Usage
```rust
unsafe {
	dangerous();
}
```

## Safe Abstractions
We may want at some point, to use unsafe functions, in a safe level, for that we may create a safe abstraction that will allow us to interface with unsafe functions:

For that, we may simply wrap unsafe code, on an unsafe scope inside a safe function. 
```rust
fn safely_dangerous() {
	unsafe {
		dangerous();
	}
}
```