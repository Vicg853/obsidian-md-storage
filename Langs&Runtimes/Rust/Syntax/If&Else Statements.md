Rust uses syntax similar to other languages.

Diferences: 
- No parenthesis
- Only accept Boolean values (does not work like JS/TS's ``if(!a) ...``):
	```rust
	let a = 10;
	if number { //<-- Illegal in rust
		
	}

	let b: Option<f32> = None;
	//You may use Some among other solutions
	if Some(value) = b {
		...
	} else {
		println!("A is not defined!")
	}
	```

Features: 
- Evaluated variable definition
	```rust
	let cond = true;
	let c = if cond { 1 } else { 2 };
	```


