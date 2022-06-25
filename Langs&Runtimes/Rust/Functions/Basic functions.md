Functions in Rust, are very similar to other programming languages functions.

With core diferences being: 
- functions that return something, must have their return type declared at the end with an ``->``
- Returns can be done using two main methods
	- the ``return`` statement:
		```rust
		fn my_func(x: i32, y: i32) -> i32 {
			println!("X is equal to {}", x);
			println!("Y is equal to {}", y);

			let sum = x + y;
		   return rum; //The return statement will return the sum expression 
		}
		```
	- Simply positioning the desired return expression at the end of the function (Rust will implicitly return it):
		```rust
		fn my_func2(x: i32, y: i32) -> i32 {
			println!("X is equal to {}", x);
			println!("Y is equal to {}", y);
			
			x + y
		}
		```

	> 	note that the semicolon also must be omitted