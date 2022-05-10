### Intro
In rust, differently than js, is not abstracted at all and can bring quite some complexity for starters.

So starting with the whole explanation of strings in Rust, with some main concepts/bullet points: 
- Strings in rust follow the UTF-8 format 
- Rust has two string variable types: ``&str`` (also reffered sometimes as a string slice) and ``String``
- 


### ``&str`` and ``String``

##### Firstly how to declare them:
```rust
let a: &str = "Hello, ";
let b: String = String::from("world!");
```

##### Specifications
Both string variable types, consist of simply an address to the real value written somewhere. These adresses can then be used in the heap, binary and stack. Although they have a similar purpose, they are formatted and  contain different characteristics:
- A ``&str`` contains two properties: the address and the variable length. But it does not own the ``str`` value, it only offers a read access to the original dynamic value: the ``str``. Plus an ``&str`` may not point to an entire string but only to a specific section from that string. 
  A ``str`` may be stored inside the binary, stack or heap memory; 
- in the other hand a ``String`` references and owns a string: it gives you mutation access to the original value, by storing three properties: the address, the length and the variable max capacity. 
  Unlike to its brother, his value will always be allocated on the heap.

The use cases for these two are:
- for variables where the objective it only to access a value: ``&str`` is the right candidate
- and where mutable variables are needed, ``String`` is the solution


### Advanced ``String`` manipulation
```rust
//Definition

let s1: String = String::from("Hello world!");
let s2: String = "Hello world!".to_string();
let s3: String = "Hello world!".to_owned(); //This means we are now taking ownership of the following string literal so... -> String by consequence

//Manipulation
let mut s1mut: String = String::from("Hello world!");
s1mut.push_str(" Make it two times!");
printlln!("{}", s1mut); 
// Hello World! Make it two times!
s1mut.replace_range(.., "I erased the previous 'Hello World's");
println!("{}", s1mut);
// I erased the previous 'Hello World's
```

- _Important characteristic about owned string_
	```rust
		let s1: String = String::from("Hello, ");
		let s2: String = String::from("world!");
		
		let s3: <String as Add<&String>>::Output = s1 + &s2;
		//Here we added two string, so, s3 = "Hello, World!", but here is the catch

		println!("{}", s1); // -> Error: borrow of moved value: s1
		//As we talked before, s1 really owns the value, just like a cup: if you throw its content into 
      //another cup, well, its content is now in the other and the original one is empty. 
      //So to do something like this wihtout losing s1 we would have to make a copy from s1 and define 
      //it as s3
	```

### Advanced ``str``/``&str`` manipulation
```rust
//Definition

let s1: &str = "Hello world!";

let example: String = String::from("Hello world!"); //Just for the example: as seen this defines a String owned literal and not a &str reference. We use this under here to show how to create a reference
let s2: &str = &example[..]; //The [..] specifies that this value should reference the example value from start to end
```


### Rust and string iteration
Rust does not allow developers to select the first character of a string for example (e.g.: ``s1[0]``), as indexes reference bytes instead of a characters. So we must select ranges:
   ```rust
   let s1: &str = "AAA";
   let s2: &str = &s1[0..4]; // "A"
   ```

But this solution up here, can be quite shitty: 
- how do we handle unicode characters that are different byte sizes
- it can a pain to get which bytes to range

For this there is a specific combinator: ``.chars()``. Which we may use with a for() loop
```rust
for c: char in "AAந".chars() {
	println!("{}", c);
}
```
But this method, has some issues itself: UTF-8 presents also a type of value called: scalar values. Scalar values consist of values that can be assembled and create small value clusters for more complex value display. These clusters are called graphemes clusters (e.g.: ந <- this is a cluster) and ( ி <- scalar value). 

For this, there is a crate: ``unicode_segmentation``. So we may import this and give a look into all characters as one: 
```rust 
use unicode_segmentation::UnicodeSegmentation;

for g: &str in 'ந'.graphemes() {
	println!("{}", g);
}
```