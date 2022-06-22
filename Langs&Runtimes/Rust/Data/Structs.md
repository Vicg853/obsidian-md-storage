Structs are almost essential in Rust. They are the most efficient way to represent data blocks on the language.

When we talk about structs on Rust, we can think of objects from other OOP languages, with the big diference being that: structs in Rust can also be defined as tuples.

To declare/create a struct you must use the ``struct`` keyword, followed by its name. You may also add generic types after its name, in more complex/necessary cases. More about struct generics [here](../Typing/Generics)

Definition: 
- Object like format
```rust
struct User {
	//Each attribute in object like structs, follows a key-value format. Apart from that, they also must have a type decalration
	usrname: String,
	email: String,
	active: bool, 
	sign_in_count: u64, //Notice structs support any data type inside them, even, other structs
}
```
- Tuples:
```rust
struct Vector(u32, u32, u32)
//Note that the syntax get slightly different: we use parenthesis to declare tuple structs instead of brackets, and attributes do not have keys and indexes are used instead. 
```

## Basic usage
Structs obviously, are just a way to "schema" and regulate data, and we must use it to define data. We call defined data as "instances". 

Instances declaration (using above examples):
- Object like 
```rust
//Definition is pretty straigfoward, using a similar syntax to a struct's declaration: [StructName] + { [data here] }
let mut new_user = User {
	usrname: String::from("vicg853"),
	email: String::from("vicg853@gmail.com"),
	active: true,
	sign_in_count: 0,
}
```
- Tuples: 
```rust
//For tuples, we could say that we define it almost as a function and its arguments. As simple as that.
let vector = Vector(0, 1, 0)
```

## Data usage and passing
_For object like structs_
To access specific values inside an object struct, we can simply use the dot notation.
- Reading ``usr = new_user.usrname`` 
- Mutating (mind the ``mut`` keyword on you variable definition): 
	 ``new_user.usrname = String::from("tumexmam")``
- Reusing values: you may reuse values from another object struct, by using the double dot notation, which is going to append inner values to the current struct:
```rust
let second_user = User {
	usrname: String::from("random"),
	email: String::from("random@example.com"),
	..new_user //Here both missing declared values will be declared with their respectives from the new_user struct, them being here: active and sign_in_count
}
```

_Tuple like structs_
To access specific values inside a tuple struct, you simply use their index, just like in lists/array, after the same dot notation:
- Reading ``x = vector.0``
- Editing ``vector.2 = 1``
- !**Note**! Tuple structs do not allow value resue for different struct types. Consider the following:
*Remember, this is not allowed and doesn't even work*
```rust
struct ThreeD_Obj(u32, u32, u32)

let cube = ThreeD_Obj(..vector) 
```
Although properties inside both structs are entirely the same, they can't be reused as they represent different structs, so probably different data parts. This rule prevents confusion between data types. The _same applies_ to _function arguments_ with different struct tuple types.


## Implementing a struct
To implement methods or other things to our struct, we need to use the ``impl`` syntax. More about it [here](../Functions/Implementations).

## Secondary concepts
- Printing structs: 
To use the ``println!()`` macro with a struct, one must implement that struct with a Display method or derivation, differently than simple types (strings, integers, etc). 
An alternative to that is using the ``{?:}`` or ``{:#?}`` syntaxes inside the macro's string brackets.
Followed by that, one must derive the struct with the default Debug, or create your own implementation of Debug on your struct