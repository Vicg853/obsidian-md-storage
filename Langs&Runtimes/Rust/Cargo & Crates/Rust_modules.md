Rust's modules, are scoped pieces of code, which we are able to define, using the ``mod`` keyword and a naming of our choice after it. 

Modules are useful to share functions among other things, to other files, allowing like that, code splitting, for cleaner workspaces.

We define a module like so:
```rust
mod my_mod {
	fn my_func() { 
		//...
	}
}
```

Modules are not limited to an only level and can be composed of many child modules, that could have their own child modules and so on...

## Privacy
Modules by default are private, that is, parent modules, can't access or see their child modules resources by default. On the contrary, child modules can access their parent and same level resources with no problem whatsoever. 

```rust 
mod my_mod {
	mod my_sub_mod {
		fn my_func2() {
			//...
		}
	}
}

fn main() {
	//This will error as the sub mod is private
	my_mod::my_sub_mod::my_fun2();
}
```

To make modules and their resources available to the outside world we can use the ``pub`` keyword before the resource's or the module's definition.

(Consider the above modified case)
```rust 
mod my_mod {
	pub mod my_sub_mod {
		pub fn my_func2() {
			//...
		}
	}
}

fn main() {
	//Now this is allowed, as our function and child module are public 
	my_mod::my_sub_mod::my_fun2();
}
```

## Parent access
As mentioned, parent modules are available to their children module and its resources. But how do we access it? 
To access a parent module we use the ``super`` keyword. 

```rust
fn from_parent_func() {
	//...
}

mod my_mod2 {
	fn my_func3() {
		//Note that here we are accessing something on the same level, so no need of the super keyword. It is only used within diferent module constraints
		my_fun4();
	
		super::from_parent_func();
	}

	fn my_fun4() {
		//...
	}
}
```

## Structs & impls & enums
Structs, impls and enums are private by default, just as functions are. But they have some small other catches to. 

#### Basics
To make a struct or an enum accessible by a parent, we must use the ``pub`` keyword before its definition.
```rust
pub enum {}

pub struct {}
```

#### Structs
The catch with enums is that... Simply defining itself as public, won't work in some cases. For  cases where we are simply using its impls or traits, the ``pub`` keyword before its definition is enough. 
But you won't be able to mutate, create, or access individual fields, as Rust makes them private by default. 

So you must place the ``pub`` keyword before defining fields you're willing to use, besides defining the struct as a public resources. 

```rust
mod my_mod3 {
	struct my_struct { 
		pub field1: String,
		field2: String
	}
}

fn main() {
	let a = my_struct {
		field1: String::from("Hello, "),
		field2: String::from("world!") //This will throw an error, at this can't be mutaded, accessed or defined.
	}

	//...
	let b = my_rand_struct_var.field1; //This works
	let c = my_rand_struct_var.field2; //This doesn't 
}
```

## Impls
For each implementation to be accessible by a parent, we must use the ``pub`` keyword, just as functions before its definition, as well as defining the struct as public.
Although, you aren't required to define fields as public, unless you're accessing them directly as mentioned above.

```rust
mod my_mod4 {
	struct my_struct { 
		field1: String,
		field2: String
	}

	impl my_struct {
		fn do_somth() -> my_struct {
			my_struct {
				field1: String::from("Hello, "),
				field2: String::from("world!")
			}
		}
		fn do_somth_else(the_struct: my_struct) -> String {
			the_struct.field1
		}
	}
}
```

## Enums
To be fair, there is no catch for enums. The things is, it can be confused sometimes to structs privacy rules, but they aren't all applied to enums. 

Enums implementations, follow the same rules, as for the enum definition itself: they both required the ``pub`` keyword, to be made public.
But enum fields, are pubic by default, as they wouldn't be that useful if they were private.

```rust
pub enum MyEnum {
	ONE,
	TWO
}
```
