Ownership is the memory management model that Rust follows, providing your app with a safe memory environment with no garbage collector or leaks. 

This model works with three specific rules, that ensures these features:
1. Each value has a variable, called its owner
2. Each value always has one and only owner
3. When a value's owner goes out of scope, the same is dropped

Let's see how these concepts apply in the real world: 
- String Moves
	```rust
		let x = String::from("Hello world!");
		let y = x;
	```
	Remember the 2nd rule?
	Well, in most programming languages, when doing this, ``x``'s' value would either be duplicated/copied into ``y``  or a second pointer would be created for this value.
	
	What actually happens in Rust, is that ``x`` 's value will be moved to ``y``, making it its new owner and x will become invalid, because it has no data. 

	Although, its possible to perform a copy, by simply using the default ``.clone()`` string method. (consider the above example)
	```rust 
	let z = y.clone();
	```

	Notice that this only occurs with Strings. For integers, th Rust will copy its value by default, instead of being moved.

- String Moves for functions
	The previous behaviour is similar on functions: when passing a String as an argument to a functions, its ownership will be handed over to the function. The same thing happens on the opposite direction: when returning a value at a function and appending this function's result to a variable, it will obtain the return's ownership. 

	```rust 
	fn a(my_arg: String) { 
		//... do something
		
		//!! Warn, we are considering that the bellow value is a String!!
		my_return //The function loses this variable's ownership
	}

	fn main() {
		let my_string = String::from("Hello World!");

		let my_result = a(my_arg); //my_arg loses ownership over the String
		//my_result now has ownership over a's return
	}
	```

	Remember, the same does not happen with integers. If we replaced the above example strings, by integers, their values would be copied from  ``my_string`` to ``my_arg`` and return to ``my_result``. 
	

## References / Borrowing 
1. At any given time, you can either have one mutable reference or any number of immutable references
2. References must always point to valid data.

#### Ref Rules explained
> _Caution_: in a same scope, we can only have **1 mutable reference**. 
> 
> If we created more than one and these were used at the same time, they could cause data corruption, as they could be writing/reading data at the same time, hence creating inconsistent data. 

> _Caution 2_: The same applies to cases mut/read references in a same scope. We can **only** define either **a mutable reference or multiple readable references**. Both can't be defined in the same scope as they could also cause data inconsistency. 

A relief pitcher is the move rule: when all your references are moved to another scope, you can now create a mutable variable and vise versa, as these values will not coexist anymore at the same scope. 

```rust
let mut x = String::from("Hi!");

let y = &x;
// let z = &mut x; This would be illegal 

println!("Message: {}", x);

let z = &mut x; //This is ok
```

> _Caution 3_: You **can't return a reference**, unless you're using a ``'static`` lifetime function. 
> Why? When a function finishes its execution, its values will be dropped, with that, a reference outside its scope would be resumed to invalid data.

## Some examples
- Working with ownership, shadowing 
```rust
fn main() {

    let mut x = String::from("Hello World");

    let y = get_slice(&x);
    println!("Y: {}", y);

    x.clear();

    let y = get_slice(&x); //* If we haven't done this shadowing then the .clear() 
    //would throw an error
	 //* As we would be accessing both an immutable and mutable reference to the
	 // same string, on the same scope.
    println!("Y: {}", y);
}

  

fn get_slice(string: &str) -> &str {
    let bytes = string.bytes();
    
    for (i, item) in bytes.enumerate() {
        if item == b' ' {
            return &string[..i];
        }
    }

    &string[..]
}
```