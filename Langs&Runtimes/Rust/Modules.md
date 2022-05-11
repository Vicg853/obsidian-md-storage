Modules in rust, distinct a bit from other language's modules. Usually other languages use directories to arrange modules while rust can have multiple modules per file, spread around one or more files. 

To define a modules on rust we use the __``mod``__ keyword e.g.: 
```rust
	// This function is now a module
	mod fn myFunc() {
		printlln!("Hello world!".to_owned())
	}
	
	//Yes it works on almost anything
	mod struct MyStruct {
		MyType: String
	}
```

But sometimes you may want to detach some things. In this case you may create another file. And now to declare it as a module inside your project you only need to use the mod keyword along the file name and path:
_file/a.rs_
```rust
	pub fn theAInFileFunc() {
		//...
	}
```
_file/mod.rs_
```rust
	//This file is considered the root for the file directory...

	//Note that to export the above file (file/a.rs) we can include it on this main module file, then it will be accessible inside the file module
	mod a;

	pub fn theModFileFunc() {
		//...
	}
```
_struct_mod.rs_
```rust
	mod struct MyStruct {
		MyType: String
	}
```
_lib.rs_
```rust
	mod file; // file/mod.rs... and file/a.rs as we included mod a; inside file/mod.rs
	mod struct_mod;

	fn main(args: struct_mod::MyStruct) {
		//...
	}
```

Above we highlight some things: 
- Rust also uses hierarchy to import modules: ``mod file/a;`` ``mod file;``, etc
- To use a module function we need to specify the imported module ``file::a::theAInFileFunc;``
- Rust mod search hierarchy works the on the following way: 
	- You define a ``mod`` keyword
	- Rust looks if the keyword contains a direct definition (e.g.: ``mod struct a { ... }``)
	- If not (e.g.: ``mod a;``) it will look for a file in the same directory as the current file
	- If not found it will then look for a folder in the current directory 
	  
### Making modules accessible outside of a file
To make anything accessible outside of a file you need to use the ``pub`` keyword, e.g.:
```rust
	pub fn a() {
		//...
	}

	pub mod b() {
		//...
	}
```

### Creating shortcuts
Sometimes things can get quite tricky to access a specific element from a module, e.g.: ``database::models::users::get::meta`` . 
To fix this we may use the __``use``__ keyword: 
```rust
	use database::models::users::get::meta();

	//Now we have a smaller sintax when accessing things inside users
	fn main() {
		let a = meta().to_owned();
	}
```
