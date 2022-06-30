We can say that traits are function templates. They are pretty similar to implementations, with a key diference: they aren't directly tied to a type and can be appended to any type, even to built-ins. 

Traits can simply define method types (their name, arguments types and return type), as well as fully define a default method execution body. 

## Definition
#### Type definition
```rust
trait MyTrait {
	fn my_method(args: i32) -> Result<(), Err>; 
}
```

#### Function body
```rust
trait MySecondTrait {
	fn my_method(args: i32) -> i32 {
		args * 2
	}
}
```

> _Note:_ a trait may implement more than one method, both with a default body or not. See the example bellow:
```rust
trait MyThirdTrait {
	fn my_method1(args: i32) -> i64; 
	fn my_method2(&self) -> i64 {
		//...
	} 
	fn my_method3(&self) -> i64 {
		//... 
	} 
}
```

## Implementing
In both definition cases, when implementing a trait to a type, you can define a specific execution body for the current implementation.
When a trait defines a default execution body, it becomes optional to implement a function body for each trait implementation. 

To implement a trait, we use the following format ``impl {Trait Def} for {Type Def}``.
```rust
struct A {
	x: i32
}

impl MyThirdTrait for A {
	fn my_method1(args: i32) -> i64 {
		//smth
	}
	fn my_method2(&self) -> i64 {
		//overiding the default trait method
	}
}
```

> _Note_ that we don't have to define ``my_method3`` as it has already a default body, also that the ``my_method2`` body is also optional, but when defined will override the default body and ``my_method1`` is implicitly required!

## Blanket implementations
You can implement traits in bulk, using types and the ``for`` keyword. 

```rust
impl MyThirdTrait for i32 {}
impl MyThirdTrait for Display {}
impl<T: Option> MyThirdTrait for T {}
```

Now we implemented the ``MyThirdTrait`` trait to ``i32`` types, types that implement the ``Display`` trait and types that implement the ``Option`` trait.