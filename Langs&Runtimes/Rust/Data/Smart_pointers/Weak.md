The weak smart pointer is pretty similar to the Reference count smart pointer with the diference of providing multiple borrowed references, instead of owned references.

It also keeps a reference count, but in this case, of non-owned references. For that you may use the ``::weak_count()`` method.

## Definition
The weak smart pointer is provided by the Rust standard library, with a ``::new()`` constructor method.

## Conversion
The Rc smart pointer and Weak smart pointer a so similar, that they can even be converted from one to another.

You can use the associate ``::downgrade()`` Rc method to converto an Rc pointer to a Weak pointer. 
```rust
let a = Rc::new(String::from("A"));

let b = Rc::downgrade(&a);
```

And the ``::upgrade()`` method to convert a Weak pointer to an Rc pointer. This method actually returns an ``Option`` enum, as if its underlying value is dropped, it will point to nothing... Hence, ``None``. 
```rust
let a = Weak::new(String::from("A"));

let b = a.upgrade();
```