The RefCell pointer abstracts borrowing from compile time, by using the ``unsafe`` feature and pushes it to runtime. 

This allows us to proceed with certain actions, where the compiler would point false positive errors, but still, you must check if everything works successfully at runtime, as rules will be now checked during this step (spiderman Ben's statement: with great powers....!!).

With the refcell pointer, you only have an only owner, while others access it as a reference. The big diference, is that it can borrow multiple mutable or immutable references, even where the compiler would throw errors.
If ownership rules are broken, the pointer will panic at runtime.

It is very useful for example, with the halting CS problem, or when dealing with immutable  implementations ``self`` references and still be able to mutate an inner struct data's.

## Definition
The Refcell pointer is exported by the ``std`` library and features a ``new`` constructor method. 
```rust 
let a = RefCell::new(String::from("A"));
```

## Usage
We now have access to two main methods: ``.borrow()`` and ``.borrow_mut()`` for immutable and mutable borrowing respectively. 

## Magic duo (aka refcell + reference count)
Check out [rc](./Rc_(aka_reference_counting)) before following with this.

A great tip is using the Refcell along the reference smart pointer. With both, we can do the impossible having multiple immutable owners of the same data and a mutable borrow at the same time. 

```rust
let a = Rc::new(RefCell::new(String::from(1)));

let b = Rc::clone(&a);

*a.borrow_mut() += 5;

println!("Num is equal to: {}", b); //Should print 6 successfully
```

