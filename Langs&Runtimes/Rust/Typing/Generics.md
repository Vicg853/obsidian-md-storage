Generics can be considered as type variables, they can help you when defining a type, that must be shared across multiple variables, functions, etc. They can also be named in any way that variables can, but are commonly defined with single letters, mainly ``T``.

You define them between angle brackets. You may define multiple ones and separate them by commas. 

Generics can be used with: Structs, Implementations, Traits, functions, arguments, returns and enums.

Then when using the resource you may either define the generic or let rust sometimes define the generic type by itself.

To forward/pass them you use the same angle brackets.

## Defining generics
#### Structs, enums and traits
To define generics on structs, you place them after its name definition:
```rust
struct A<T> {
	x: T
}
```

The same applies to Enums:
```rust
enum B<T> {
	VARIANT(T)
}
```

> _By the way:_, both the option and result enums use generics: the option enum having one generic that will be used by the ``some`` variant and the result two: one for the error type and another for the result type.

It also can be applied to traits:
```rust
trait C<U> {
	//...
}
```

#### IMPLs
To define generics on implementations, you place them after the ``impl`` keyword:
```rust
impl<T> A<T> {
	//...
}
```

#### Returns
We may also specify a function's return type:
```rust
fn my_func() -> i32 {
	//...
}
```

## Type narrowing
You may sometimes, need to limit the types that can be passed to a generic, you can do that, in the same way as if you were defining a variable's types: 
```rust
struct E<T: i32> {
	//...
}
```

You can define many types using the ``+`` : 
```rust
struct F<T: i32 + i64> {
	//...
}
```

You can think of this as typescript's ``extends`` keyword.

You can also use trait bounds, to narrow down generics to only types that implement a certain trait (check out more about [trait bounds](./Trait_bounds)):
```rust
struct G<T: Display + Clone> {
	//...
}
```

## Traits and Impls "type filtering"
When defining implementations and traits into structs/enums, using generics, you may filter by type, which implementations and traits are implemented.

```rust
impl<U> A<U> { 
	fn a(&self) { 
		&self.x
	}
}

impl A<i64> {
	fn b(&self) {
		&self.x
	}
}
```

> _Explanation:_ In this case, the ``a`` method will be available to any data implemented with the ``A`` struct. But the ``b`` method, will only be available to data implemented with the ``A`` struct where the generic is of type ``i64``. 

## ``where``
On ``impl``s, ``trait``s, ``enum``s, ``struct``s and ``fn``s generics can sometimes get quite long and complicated. For that the ``where`` keyword exists. It is a syntax sugar, that should be defined under the above mentioned element's definition. 

There you can specify in a more readable way, each's generic type starting by a ``where`` keyword and a comma at the end of each generic's type definition. 

```rust
fn my_func<T, U>() -> i64
	where T: Display,
			U: Copy, 
{

}
```

It is usually recommended to be used along trait bound definitions. 

## Performance
There are no performance overheads when using generics. Rust only does generic type checks at compile time and removes them at from runtime code. 

Rust actually generates all the necessary code for each generic type case. So for as an example when using the ``A`` struct to create a ``let x`` variable with a i32 value and another ``let y`` variable with i64: Rust will create two different struct implementations, one for the i32 and another for i64.



