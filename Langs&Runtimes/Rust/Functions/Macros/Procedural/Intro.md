Procedural macros, are the attributes we usually see on top of structs and other data types. They are used to extend current code and have function like declaration, instead of declarative macros that replace code. 

They can be assigned to three different procedural macro types: custom derive, attribute like and function like. 

Procedural macros have an only complexity rule, that should be removed in the future: they must be store in their own library crate, that contains a ``proc-macro`` attribute, set to ``true`` under the ``[lib]`` section on its ``Cargo.toml`` file.

They are all defined with the following syntax: defining a function, which's name will be the macro's name, an only input argument (the data which we will work on top of) and a return type.
Also we must specify which macro type it corresponds to by macroing it itself.

Both the argument's and return's input type are of ``TokenStream`` which is imported from the ``proc_macro`` crate (imported with the ``extern crate`` statement). Tokens correspond to the smallest syntax elements: literals, statements, etc...

## Definition by example
```rust
extern crate proc_macro;

use proc_macro::TokenStream;

#[proc_macro_derive(MyMacro)] //Here we are definning it as a derive type
pub fn my_macro(input: TokenStream) -> TokenStream {
	//... our macro inner workings
}
```

## Useful crates
When working with procedural macros, as we are manipulating existing code, we may also want to interact with it. 

To do it, two very useful crates are: 
- ``syn`` that allows us to parse Rust code into operable data structures
- ``quote`` can transform ``syn``'s data structure back into Rust code