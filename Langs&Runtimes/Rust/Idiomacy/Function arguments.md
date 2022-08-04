Functions are used everywhere and here are some idiomatic Rust function tips to keep in mind:

## Coercion
Some types, have coerced versions of themselves, e.g.: ``&String`` can be coerced to ``&str``, which means that a function accepting ``&str`` can accept both ``&String`` and ``&str`` types, making your code more dynamic. 

Its very useful to think about coerced types when creating function arguments.

Apart form Strings, here are some other cases where this can be applied. 

#### Smart pointer coercion
When passing reference arguments, that could possibly wrapped by smart pointers, define the respective type alone, without wrapping it with a smart pointer.
This coercion is possible, as when passing smart pointer references it will be automatically be converted to a direct reference to its underlying data. With that, your function may accept both the actual type and its wrapped version. 

```rust
struct MyStruct {}
fn a(arg: &MyStruct) { //This instead of &Box<MyStruct> for example
	//...
} 

let var1 = Box::new(MyStruct {});
let var2 = Box::new(MyStruct {});

a(&var1);
a(&var2); //Both calls work
```

#### vector coercion
Use arrays instead of vectors as argument type. Arrays aren't compatible to vectors, as vectors may have variable size, but, vectors are compatible to the array type. So you may coerce and argument to a defined array type, to accept both arrays and vectors.

```rust
fn b(arg: &[String, 2]) { //This instead of &Vec<String> 
	//... 
}

let vec = vec!["A".to_owned(), "B".to_owned(), "C".to_owned()];
let arr: [String, 2] = ["A".to_owned(), "B".to_owned()];

b(&vec);
b(&arr); //Both calls work
```