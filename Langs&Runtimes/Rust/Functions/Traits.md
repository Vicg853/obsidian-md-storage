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
You can implement traits in bulk, by implementing all elements that match a certain requirement, e.g. anything that implements another trait, using types and the ``for`` keyword. 

```rust
impl MyThirdTrait for i32 {}
impl MyThirdTrait for Display {}
impl<T: Option> MyThirdTrait for T {}
```

Now we implemented the ``MyThirdTrait`` trait to ``i32`` types, types that implement the ``Display`` trait and types that implement the ``Option`` trait.

## Static and dynamic dispatch implementations
In some cases, [trait bounds](../Typing/Trait_bounds) with generics may be more than enough: the compiler creates an implementation for each case and uses them when respectively required. 

But sometimes, we may need more versatility, where a same implemented method must be genuinely used across multiple types and generics won't fit. That's when the called a dynamic dispatch, enters the scene.

When the compiler applies dynamic dispatch, instead of generating compile time variations, it figures out things at runtime. This can provide versatility while causing a slight runtime overhead.

#### Usage
To declare when a dynamic dispatch should be used, we use the ``dyn`` keyword, before trait implementation bound definition.
```rust
trait MyTrait {
	fn world(&self) {}
}

struct A {
	hello: Vec<Box<dyn MyTrait>>
}
```

> On the case above, now, elements passed to the ``A.hello`` struct, will be dynamically determined at runtime and the compiler will only an only ``A`` variation. When using the ``hello`` field in any way, its type will be determined at runtime.
> If we used generics instead, and a ``static`` implementation pattern, the ``A`` struct would probably be replicated as many times as required, preventing runtime check.

#### Rules
As usual, apart from "personal" decisions,  a set of rules will determine when each case must be used. The rules for static/dynamic dispatch implementations are called Object safety. 

When you are object safe, generics can be used. Object safe means:
- The implementation method's return type is not ``Self`` 
- The implementation method's parameters are not defined based of generics

If one of both rules can't be followed, the Rust compiler won't be able to define things at compile time and will require a runtime decision. 