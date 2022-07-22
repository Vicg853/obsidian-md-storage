Sometimes, we may want to differ types one from another. Rust allows us to do this in two main ways:

## The ``type`` keyword (type alias)
Type aliases similarly to generics, coud be compared to type variables. They allow us to reference another type and use it in many places, without repetition.

They are useful when types aren't usually going to change from case to case and/or should be passed as variables, arguments, etc... 

It is defined just like variables are: ``type`` keyword, followed by the desired type name, then an ``=`` sign, plus the underlying aliased type.
As for usage: just reference it as any other built-in type.

```rust
fn a() {
	//Type definition here
	type Thunk = Bo<dyn Fn() + Send + 'static>;

	//Usage
	let f: Thunk =
		Box::new(|| println!("hi"));

		fn takes_long_type(f: Thunk) {
			//---
		}
}
```

## Newtype pattern
The new type pattern is particularly useful when working with both external types and traits. It allows us to create new types from local or external types.

It simply consists of defining a tuple struct, wrapping the respective type.

```rust
struct MyNewType(i32);
```

You can see a case of external traits + external type implementation [here](../Functions/Traits/Newtype_pattern).