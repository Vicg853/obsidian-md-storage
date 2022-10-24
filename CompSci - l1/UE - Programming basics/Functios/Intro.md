Functions are a group of defined actions, that can be called and executed the same way multiple times, to accomplish a specific defined action.

```rust
fn a(): () {
	println!("Hello world!");
	()
}
```

#### Fns and memory
Each function call creates a new memory space on the stack, where values used inside this function will be stored. 

Functions can't directly share memory.

#### Communication types
Communication and data sharing between functions is essential, otherwise, all would be useless. 
As sharing memory is not an option, we do it through arguments, or returns. 

There are two main sharing types: 
- value sharing: when we pass variables through arguments or returns
- references: by sharing variable adresses to other spaces in memory and therefore giving access to them

