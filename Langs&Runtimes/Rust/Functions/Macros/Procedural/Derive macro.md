This type, only works on ``struct``s and ``enum``s and must be passed as an argument to the ``derive`` macro. 

Derive macro functions, accept an only ``TokenStream`` argument, that will receive the respective ``enum`` or ``struct`` types. 

As for definition, it must be macroed with the ``proc_macro_derive`` macro attribute, which accepts the macro name as argument.

```rust 
//Macro def 
#[proc_macro_derive(MyMacro)]
fn my_macro(my_type: TokenStream) -> TokenStream {
	//... underlining macro's source
}

//Macro usage
#[derive(MyMacro)] 
struct A {
	//...
}
```
