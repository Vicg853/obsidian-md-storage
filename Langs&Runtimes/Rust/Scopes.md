## Ownership and scopes
Something to notice is that variables change on a single scopes. Let's think of it as a 'virtual' scope, when we are manipulating and moving variables. 

With that said, let's say that we have a variable, on a certain 'virtual' scope, when we move this value into a function (notice, we are _moving_ it and not _borrowing_ it). 



## Tips & tricks
- In Rust you can create a new scope with no functions or whatsoever, just use brackets and a new child scope will be created
```rust 
fn main() {
	{
		let y = String::from("Hello World!")
	}
}
```