We may stumble cases were we must borrow values, without respecting the memory safe borrowing rules. 

For that, Rust has the unsafe raw pointers. Differently than smart pointers, raw pointers, do not respect ownership rules. 
As an example: we may create two raw pointers, an immutable and a mutable one, at the same time, inside the same scope.

## Definition
We define them using the ``as`` keyword, followed by an ``*`` and then the desired type: ``const``/``mut``/... + type (e.g.: ``i32``)

```rust
let mut a = 5;

let b = &mut a as *mut i32;
```

> _Note_ that Rust doesn't completely ignore its surroundings. It still does some type checking, such as if ``a`` is actually an ``i32`` and if ``a`` is actually mutable, allowing us to borrow or not immutable raw pointers from it. 

> _Small Fact_: in this example, ``b`` will actually be safe, as it is a reference to ``a``. If we for example, tried accessing a random memory address noted by a hex ``0x012345usize``, it may or not invalid. 

## Notes
- Raw pointers are not automatically cleaned up
- You can not guarantee that raw pointers, point to unsafe memory 
- You can only dereference raw pointers inside an ``unsafe`` block

## Access
As said, you can only access a raw pointer's underlying value, aka dereference it, inside an ``unsafe`` block.

(Consider the example above)
```rust
unsafe {
	println!("a = {}", *b);
}
```