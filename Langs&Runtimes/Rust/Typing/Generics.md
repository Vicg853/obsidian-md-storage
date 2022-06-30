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

## Generic limitation
You may sometimes, need to limit the types that can be passed to a generic, for that you may use ``:`` after the generic's definition and specify its types. 
```rust
struct E<T: i32> {
	//...
}
```

You can define many types using the ``+`` : 
```rust
struct F<T: i32 + i64>{
	//...
}
```

You can think of this feature, as the typescript ``extends`` keyword.

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

> _Explanation:_ In this case, the ``a`` method will be available to any data implemented with the ``A`` struct. But the ``b`` method, will only be available to data implmented with the ``A`` struct where the generic is of type ``i64``. 




