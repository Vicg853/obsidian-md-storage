Something that helps us a when working with Rust's ownership systems are _references_ (usually called as borrowing too). 
References can be used when we want to access data, without taking ownership for it. 

To create a reference, we use the ``&`` symbol before the String type and variable usage. 
Check [this](References.md) out to know more about defining references

## Reference rules
1. At any given time, you can either have one mutable reference or any number of immutable references
2. References must always point to valid data.

#### Ref Rules explained
> _Rule nº 1_: in a same scope, we can only have **1 mutable reference**. 
> 
> If we created more than one and these were used at the same time, they could cause data corruption, as they could be writing/reading data at the same time, hence creating inconsistent data. 

> _Rule nº 2_: The same applies to cases mut/read references in a same scope. We can **only** define either **a mutable reference or multiple readable references**. Both can't be defined in the same scope as they could also cause data inconsistency. 

> _Rule nº 3_: You **can't return a reference** to a variable owned by the current scope, unless you're using a ``'static`` lifetime function. 
> Why? When a function finishes its execution, its values will be dropped, with that, a reference outside its scope would be resumed to invalid data.

These rules imposed by the compiler prevent both data races and dangling references issues. 
Data races are when:  
- Two or more pointers access the same data at the same time.
-  At least one of the pointers is being used to write to the data.
-  There’s no mechanism being used to synchronize access to the data.
And dangling references is when we have a pointer to non-existent/moved data.

## Scopes
As stated by the rules, we can't neither have multiple mutable references, nor immutable variable(s) and a mutable reference at the same time on a respective scope. But, there is a small "hack" that we may use to do it: by creating scopes using ``{ }``.

```rust
let my_string = Stirng::from("A");

{
	let a = &mut my_string;

	a = String::from("AA");
}

{ 
	let b = &mut my_string;
	
	b = String::from("B");
}

println!("Updated my_string to: {}", &my_string);

```

## References and ownership 
You must take care when using references. A set of rules provide memory safety when using them, so take a look [here](./Ownership).