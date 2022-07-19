In some cases, a trait's method, may depend on other traits. 

Super traits fix that. They are a simple definition, that forces us to implement a certain other trait to use the current one, very similar to the ``(arg: ipml MyTrait)`` format on function trait bounds.

In a nutshell, they allow us to declare that a trait requires that the type is also implementing another trait. 

It is done at trait definition, after its name followed by an only column and then the required trait.

```rust
trait A { }

trait B: A { }

struct MyStruct { }

impl B for MyStruct { }
impl A for MyStruct { } //We are required to do this, as the B trait requires A trait
```