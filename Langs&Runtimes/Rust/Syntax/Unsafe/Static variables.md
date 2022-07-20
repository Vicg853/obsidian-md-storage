Global variables are actually a thing in Rust, but they are special quite special. 

``let``s and ``const``s can't be declared as globals, we must use instead the ``static`` keyword.

The thing with static variables, is that they aren't safe, as for example, a defined static variable could be accessed more than once by two different threads at a given time, possibly causing invalid behaviour.

``static`` also feature a couple other characteristics and rules: 
- They may be mutable. To define them as mutable, just use the ``mut`` keyword as in ``let``s and ``const``s;
- They can be accessed across multiple threads at once;
- They have a static memory address. This rule is even stronger than for variables, their address is the same for the entire program's runtime and will never change throughout its lifetime
- It value must have a static lifetime
- Types MUST be annotated

## Definition
```rust 
static a: &str= "A";
static mut my_static_mut: &str = "I'm mutable";
```

## Access and mutation
(consider the example above)
```rust
unsafe {
	println!("A = {}", a);

	my_static_mut = "Modified";
	println!("Mutable Static = {}", my_static_mut);
}
```
