Something that helps us a when working with Rust's ownership systems are _references_ (usually called as borrowing too). 
References can be used when we want to access data, without taking ownership for it. 

To create a reference, we use the ``&`` symbol before the String type and variable usage. 
Check [this](References.md) out to know more about defining references

## Refrence rules
1. At any given time, you can either have one mutable reference or any number of immutable references
2. References must always point to valid data.

#### Ref Rules explained
> _Rule nº 1_: in a same scope, we can only have **1 mutable reference**. 
> 
> If we created more than one and these were used at the same time, they could cause data corruption, as they could be writing/reading data at the same time, hence creating inconsistent data. 

> _Rule nº 2_: The same applies to cases mut/read references in a same scope. We can **only** define either **a mutable reference or multiple readable references**. Both can't be defined in the same scope as they could also cause data inconsistency. 

A relief pitcher is the move rule: when all your references are moved to another scope, you can now create a mutable variable and vise versa, as these values will not coexist anymore at the same scope. 

```rust
let mut x = String::from("Hi!");

let y = &x;
// let z = &mut x; This would be illegal 

println!("Message: {}", x);

let z = &mut x; //This is ok
```

> _Rule nº 3_: You **can't return a reference**, unless you're using a ``'static`` lifetime function. 
> Why? When a function finishes its execution, its values will be dropped, with that, a reference outside its scope would be resumed to invalid data.

## References and ownership 
You must take care when using references. A set of rules provide memory safety when using them, so take a look [here](./Ownership).