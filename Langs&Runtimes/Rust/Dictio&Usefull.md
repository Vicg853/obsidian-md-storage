### Useful/quick combinators
- ``.concat()``: Concats distinct variables
	```rust
	let a: String = ["Hello, ", "world!"].concat();
	```


### Useful/quick macros
- ``concat!()``: Concats distinct variables
	```rust
	let a: &str = concat!("Hello, ", "world!");
	```
- ``format!()``: Concats distinct variables
	```rust
	let a: String = format!("{}{}", "Hello, ", "world!");
	```

### Commands
- ``cargo vendor``
Generates all vendor required manifests in a specific folder.