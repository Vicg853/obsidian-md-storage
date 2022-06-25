Traits are almost like implementations... The key diference is: implementations are tied to a struct, while traits aren't. 

Traits are defined by themselves, alone and than, implemented to a struct. We can think of them as components, that can be implemented by several structs. 

A simple trait on a struct example:
```rust
	struct User {
		id: String,
		name: String,
		comment: String
	}
	
	struct Post {
		id: String,
		author: String,
		desc: String
	}
	
	trait Summarize {
		fn summarize(&self) -> String {
			//your code here
		}
	}

	impl Summarize for User { }
	impl Summarize for Post { }

	//Now we have a summarize method on both User and Post
```

## Type only
Rust traits can also be used as type only declarations, and make way for case by case implementation (consider the above example):
```rust
trait FetchStruct {
	fn get(id: String) -> Self;
}

impl FetchSstruct for User {
	fn get(id: String) -> self {
		// Fetch users logic
	}
}

impl FetchSstruct for Post {
	fn get(id: String) -> self {
		// Fetch posts logic
	}
}
```

## Tips&tricks
- Rust default types, structs, etc... Can also connect to traits:
```rust 
trait Num {
    fn from_i32(n: i32) -> Self;
}

//See 
impl Num for f64 {
    fn from_i32(n: i32) -> f64 { n as f64 }
}

let _: f64 = Num::from_i32(42);
let _: f64 = <_ as Num>::from_i32(42);
let _: f64 = <f64 as Num>::from_i32(42);
let _: f64 = f64::from_i32(42);
```