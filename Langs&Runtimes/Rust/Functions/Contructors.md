In rust structs can be implemented and functionalities can be added onto or on-top of data/types. And constructors are one of the possible alternatives:
We could say that this is similar than building classes on javascript....

```rust 
	struct User {
		id: u32;
		pub name: String;
		pub role: String;
	}

	//This is an implementation of user
	impl User {
		// And here we can see: we're building a function on top of a struct
		fn new_user(name: String, role: String) -> Self {
			Self {
				id: rand(),
				name,
				role,
			}
		}
	}
```

_Info_: here we see that this function returns a ``Self`` type, which means that this function will return a data-type of ``struct User`` (where self is the current struct we're implementing). In a nutshell we just created a constructor!!

### Default impl

We can also use the ``Default`` implementation convention, that implements a default constructor for a data-type. 

For that we use the following format: 
```rust 
	impl Default for User {
		fn default -> Self {
			//...
		}
	}

	//Now capbilities like using the following combinator are an option:
	User::new_user("Victor".to_owned(), "Admin".to_owned())
			.unwrap_or_default();	
```

### Default impl derivation
We may also add a derivation to a struct, where rust will automatically add default values:
```rust
	#[derive(Default)]
	pub struct Post {
		content: String,
		tags: Vec<String>,
		likes: u32,
	}

	//This will return 
	{
		content: "",
		tags: [],
		likes: 0
	}
```

Another derivation option recommended by the Let's Get Rusty channel is the ``derive-new`` crate (following the above example): 

```rust
	#[derive(Default, new)]
	pub struct Post {
		#[new(value = "\"This post is empty :(\".to_owned()")]
		content: String,
		#[new(value = "vec![\"No tag\"]")]
		tags: Vec<String>,
		likes: u32,
	}

	//This will return by default
	{
		content: "This post is empty :(",
		tags: ["No tag"],
		likes: 0
	}
```