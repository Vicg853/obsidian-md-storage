As Rust isn't an OOP language, constructors don't follow an specific set of rules and naming. But, there are conventions to help keep things straight.

There are two main conventions, that can be easily implemented using two different traits:

## Default
The ``Default`` trait, included on the ``std`` library, requires us to define a ``default`` method. This method shall require or not a set of arguments used to initialize the respective data and must output an instance of ``Self``.

```rust
struct MyStruct {}
impl Default for MyStruct {
	fn default() -> Self { 
		MyStruct { } 
	}
}
```

You may also derive data structures with the ``Default`` macro, if all underlying data implement the ``Default`` trait themselves.

## New
The new implementation actually has some additional requirements and a small diference. 

#### Convention
First, there is a convention of implementing a ``new`` method to data structures, although, there is no "New" trait by default or in the ``std`` rust library.

#### ``derive-new`` crate
But there actually is a trait that allows us to derive data with a ``new`` macro: the ``derive-new`` crate. It can be imported using cargo, which allows us to then import and very easily derive data with it.

We must macro each underlying data with the ``new`` attribute-macro. 

When a data's default value is not defined within definitions, then we this macro will automatically require that arguments to the underlying data are passed to it. 
As for data with defined defaults, they must be modified after definition, arguments aren't accepted. 

```rust
use derive_new::*;

#[derive(new)]
struct A {
	#[new(value = "Hello World!")] //Here we are defaulting field1 to this value when calling the new method.
	field1: String,
	#[new(default)] //It even allows us to use the pre-implement its default value
	field2: u32,
	field3: String
}
```