Differently than derive macros, custom attributes can extend more than only ``struct``s and ``enum``s, they can also extend other types such as functions.

They are defined and used similarly to derived macros, they just don't require you to derive them.

Also, they receive two arguments: one with arguments passed to this underlying macro and another with the respective macroed type. Both are of ``TokenStream`` type.

Attribute like macros are extended by the ``#[proc_macro_attribute]`` attribute macro.

They are called as functions: ``#[MyMacro("A")]``.

```rust
//Definition
#[proc_macro_attribute]
pub fn a(args: TokenStream, el: TokenStream) -> {
	//...
}

//Usage 
#[a("b")]
fn my_func() {
	//...
}
```