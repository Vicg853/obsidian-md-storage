_Check out [traits](Langs&Runtimes/Rust/Functions/Traits/Intro.md) before!_

Associate types are pretty similar to generics: you define type variables, that can be used across multiple components.

They must be used within traits and have an additional restriction that differs them from generics: all implementations of the respective trait across a same component, MUST SHARE the SAME concrete type.

For example, you can't implement to a same component two times, where one of them features an associate type ``x`` of type ``u`` and another features that same ``x`` associate type of type ``v``:
```rust
trait MyTrait {
	type A;
	//...
}

struct MyStruct {
	//...
}

impl MyTrait for MyStruct {
	type A = i32;
	//...
}

impl MyTrait for MyStruct {
	type A = isize; 
	//This should either be i32 or the above definition should be o isize
	//...
}

```
This |^| _is not_ allowed.

