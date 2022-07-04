The box smart pointer, is included into the std rust library, it allows you to allocated data on the heap, instead of the stack, at runtime.

They accept any type of data and point to the allocated data on the heap, making it useful for when you need to store large and variable amounts of data, that can't be stored on the stack. 

Among other smart pointers, they are pretty lightweight (apart from the data stored on the heap), as they only store the data's length and capabilities to transfer ownership.

When it goes out of scope, it makes the underlying data be dropped from the heap as well.

## Simple Declaration
#### Literal definition
```rust
let a  = Box::new(5); // It's an example, please don't this...
println!("A is equal to, {}", a);
```

#### Type definition
A struct that accepts a generic of type T: ``Box<T>``
```rust
enum A {
	Box<B>,
	C
}
```

## Example (lisp lang ``cons`` paradigm)
On the lisp programming language, there a ``cons`` paradigm. In a nutshell, it is a recursive tuple type that references itself (more about it [here](https://en.wikipedia.org/wiki/Cons#:~:text=In%20computer%20programming%2C%20cons%20(%2F,%2C%20or%20(cons)%20pairs.)).

In Rust this practice isn't common, but can be used as a good example for the Box smart pointer.

Consider the following ``cons`` enum
```rust
enum List {
	Cons(i32, List),
	Nil
}
```

> The above case will cause an error, as this data should be stored on the heap when ran by a function, but, Rust can't figure out how much will it weight on the heap, hence how much memory it should allocate on the heap.
> Wy? Because in this case, the ``Cons`` variant, holds a List, that may hold another ``Cons`` variant and so on... Causing a possible infinite loop of ``List`` enums. 

We may use the Box smart pointer. This way, Rust knows how much the first recursive level of  weights, as smart pointers have a fixed length. As for the nested data, it will have a known length + it al nested data will be stored on the heap, where length limits aren't that constraint.
```rust
enum List {
	Cons(i32, Box<List>),
	Nil
}
```