Shortly: traits are almost function structs, that can then be implemented to any struct or resource.

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


