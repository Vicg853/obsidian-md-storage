As stated on the intro, there are three different macro extensions.

## Derive macros
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

## Custom attributes
Differently than derive macros, custom attributes can extend more than only ``struct``s and ``enum``s, that is 

Defining a custom attribute is done similarly to a derive macro, the main difference being that it must have a first argument that will receive arguments passed to this macro and a second one that will contain the macroed element, both being ``TokenStream``s. Also it must be this time extended by the ``#[proc_macro_attribute]`` macro.

##