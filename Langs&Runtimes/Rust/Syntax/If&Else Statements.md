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

## Variable definition
You may use If conditions to define variables based of conditions. There are two ways of applying this:

**_Condition based_**
This can be used when a condition must be achieved for a scoped value to be return, or else something else to be done.
```rust
let cond = true;
let c = if cond { 1 } else { 2 };
```

**_Result based_**
A similar way, but without condition and the ``if`` keyword itself, where the value assignment itself is already a condition: if the value returned by a function or expression doesn't match the lefthand pattern or type. If at least one of the requirements aren't meet, Rust will forward with the else statement.
```rust
let (Some(a), Some(b)) = (a(), b.get()) else {
	panic!("Oups!")
};
```




