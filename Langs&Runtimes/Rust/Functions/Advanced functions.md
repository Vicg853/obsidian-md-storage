## ``fn`` pointer keyword 
We may use the ``fn`` keyword as an arg type to infer that the same receives a function. 

Also, we must implicitly define the underlying argument function's argument types between parenthesis and an arrow followed by the return type.

```rust
fn b(arg: i32) -> i32 {
	arg
}

fn a(b: fn(i32) -> i32) -> i32 {
	b(2)
}

a(b)
```

## ``Fn`` pointer trait bound
We also may use the ``Fn``  trait bound, in this case, for both closures and functions. This trait bound can be passed standalone or with parenthesis, plus argument/return types.

```rust
fn my_func(fn_or_clos: Fn(i32) -> i32) { /*...*/ }
fn my_func_alt(fn_or_clos: Fn) { /*...*/ }
```

## ``FnMut``, ``FnOnce`` trait bounds
Both the ``FnMut`` and ``FnOnce`` trait bounds can only be used for closures. 

The difference to ``Fn``? When working with closures, the ``Fn`` trait bound, indicates that this closure will only borrow immutable references from it surroundings. 
While the ``FnMut`` will borrow mutable variables from it surrounding and ``FnOnce`` will move it surroundings into its scope, thus only running one time and the "Once" in its name.

```rust
fn my_clo_func(clos: FnMut) { /*...*/ }
fn my_clo_func(clos: FnOnce(i32) -> i32) { /*...*/ }
```

## Tuple structs and enum variants
Something interesting to now, is that Tuples in Rust behave somewhat like functions: they require a number of arguments and return either its underlying struct or enum variant type.

So they actually can be passed as a functions argument. 

Lets consider this case from the built-in ``.map()`` method
```rust
enum Status {
	Value(i32),
	Stop
}

let list_of_statuses: Vec<Satus> =
	(0u32..20).map(Status::Value).collect();
```
> Explanation: the ``.map()`` method accepts a closure type. Here, we are passing a tuple like variant from the ``Status`` enum, which the ``.map()`` method will call just like a function..

## Returning closures
We may also return closures from functions... But there is a catch with it.

#### Simple usage
In simpler cases, when returning a closure as function result, we just define the return type, as an function trait bound ``impl`` and return it.

```rust
fn return_closure() -> impl Fn(i32) -> i32 {
	|x| x + 1
}
```

#### Complex usage
But sometimes, we may want to return multiple closures, based on a certain input... But this isn't allowed by default: _multiple impl returns, must share the same type_. 

And although we are returning two closures, that maybe even share the same format, they still consist of two completely different types. 
Thus, we need to annotate the return type as a trait object and wrap the closure around a smat pointer, as Rust can't find out the compile time size.

```rust
fn returns_mult_closures(a: i32) -> Box<dyn Fn(i32) -> i32> {
	if a > 0 {
		Box::new(move |b| a + b )
	} else {
		Box::new(move |b| a - b)
	}
}
```