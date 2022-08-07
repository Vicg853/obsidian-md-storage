Sometimes, naming can be tricky and methods may get duplicated. With Rust, this is not a problem. 

The compiler allows you to create methods across traits and data types "natural" implementations, that can later be joined together and share equally named methods.

You just need to tell the compiler your current intentions, otherwise by default, it will use directly implemented methods (when using the ``.``method``()`` notation). 
Then there are two different scenarios as for intention declaration.

Note that isn't the same as function overload: some data can't have equally named methods in its root ``impl`` block. You may only have equally named methods on a data type where each originates from it's own trait definition block.

#### normal methods
When a trait's method accepts a ``&self`` argument, Rust can easily figure things out. So we simply use the trait name and double columns, followed by the chosen method, which will receive the desired type variable that implements this trait: ``MyTrait::my_method(&my_struct_that_impls_MyTrait)``

```rust
struct MyStruct { }

impl MyStruct {
	fn fly(&self) -> { } // (1)
}

trait MyTrait {
	fn fly(&self) -> { } // (2)
}

impl MyTrait for MyStruct { }

let my_var = MyStruct { };

my_var.fly(); //The method implemented at (1)
MyTrait::fly(&my_var); //The method implemented at (2)
```

#### Associate methods 
When working with duplicated associated methods, Rust can't just figure ou about the data type implementations and etc...

So, there for that we use the ``as`` syntax between arrow brackets: ``<MyStruct2 as MyTrait2>``.
This will tell Rust, that we are looking for method on the ``MyStruct2``'s ``MyTrait2``'s implementation. Then, followed by double columns, chosen method and parameters.

```rust
struct MyStruct2 { }

impl MyStruct2 {
	fn fly() -> { } // (1)
}

trait MyTrait2 {
	fn fly() -> { } // (2)
}

impl MyTrait2 for MyStruct2 { }

let my_var2 = MyStruct2 { };

MyStruct::fly(); //The method implemented at (1)
<MyStruct2 as MyTrait2>::fly(); //The method implemented at (2)
```
