Functions macros are like Rust's functions, however they are more flexible. They will operate on Rust code and output Rust code and accept a variable number of arguments.

They must be extended by the ``#[proc_macro]`` attribute macro and are called just like declarative macros, but mixed with a function call like syntax: _macro name_ + ``!(`` + arguments + ``)``

```rust
//Definition 
#[proc_macro]
fn my_macro(item: TokenStream) -> TokenStream {
	//...
}

//Usage
let a = sql!(SELECT * FROM posts WHERE id=1);
```