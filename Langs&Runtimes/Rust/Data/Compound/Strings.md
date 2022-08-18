Strings are actually quite complex. They are more than just double quoted wrapped text. Computers and humans interpret this data VERY differently, and Rust, being mainly a systems language, exposes this complexity.

A String in Rust, is a collection of bytes. The only raw language type of a string in Rust, is the ``str`` type. But we usually will use and talk about both its borrowed form ``&str`` and the ``String`` type provided by the std library. 

For staters here are some main concepts/bullet points: 
- Rust Strings in general, follow the UTF-8 format, that means. This also means that strings' bytes have variable length: 1-4 bytes.
- As said we usually use two string types: ``&str`` (also referred sometimes as a string slice) and ``String``
- Both ``&str`` and ``String`` types, must be annotated with double quotes: ``"``, as opposed to characters
- Both string types follow different storage methods:
	- ``String``s are stored on the heap
	- ``str``s (yes, the missing ``&`` is on purpose) on the program's binary and are immutable
	- and ``&str`` on the stack, and can either reference a ``String`` or a ``str``


Declaration:
```rust
let a: &str = "Hello, ";
let b: String = String::from("world!");
```

## Specifications
Both string variable types, consist of simply an address to the real value written somewhere. These adresses can then be used in the heap, binary and stack. Although they have a similar purpose, they are formatted and  contain different characteristics:

#### ``&str``
First, string slices are actually pointers to string stored in the program's binary or to other stored string. They don't own the actual string's data and aren't able to mutate it, having only read access to it. 
String slices, as their nickname mentions, can also point only to a slice of a String. 

They are composed of two main properties: 
- The String's address 
- The string's or slice length

#### ``String``
On the other hand, a string actually owns its data while also being of a pointer. Don't get it wrong, it has write access to it, but when as it runs on the stack and its value is mutable, with that. of variable size, its value must be stored on the memory's heap.

As for what it is composed of:
- The string's address
- Its length (the entire length, no slices)
- And it's max capacity

## ``String`` definition
There are two main ways to define a ``String`` type: converting a ``&str`` into a ``String`` or passing a ``str`` to the ``String``'s ``from()`` method.

```rust
let a = String::from("A");
let b = "B".to_string();
```

As ``String`` are scalar types, when passing it to a function, variable, etc, without specifying it as a reference, such element will take ownership of this respective ``String``.

```rust
let foo = String::from("foo");
let bar = String::from("bar");

let added = foo + &bar; // foo loses ownership from "foo", while bar keeps its ownership over "bar"
```

## ``&str`` definition
First thing to note is: ``&String`` can be coerced to a ``&str`` type.

The ``&str`` type, as said, is a reference to a slice of either a ``str`` or ``String``, so, we may declare it in three ways: using a reference annotation (``&``) on a ``String`` or ``str``, using the ``.as_str()`` method, or defining a reference range like so ``&my_str_or_String[..]`` (this references the entirety variable of our variable).

```rust
let a = String::from("Hey!");

let b = &a;
let c = a.as_ref(); //Note that, we reference it multiple times, as we are not taking owenship at any point and only referencing a
let d = &a[..];
```

## Rust and string iteration
The UTF-8 is pretty good, it provides a wide variety of human characters and symbols. But, it can cause difficulties when handling them with code.

When talking of the human definition of characters in UTF-8, we talk about a set of 1 to 4 bytes. So, if we tried, in code, to return a ``String``'s  first index (``[0]``), we would actually be returning the first byte of this string, which could mean something sometimes, but for some human characters, could mean nothing, as it could be composed of more than one byte.

So Rust, actually panics, if we try to select a range of index from a String, this prevents us from causing future bugs caused by misconceptions and to prevent performance issues, as it would have to runs through the entirety of the string, to get knowledge of each character and define a length on top of them.

Hopefully, Rust provides a method, that returns an iterator of characters: ``.char()`` method, implemented to each String type.
```rust
for c: char in "AAந".chars() {
	println!("{}", c);
}
```

The thing is, there is another concept in UTF-8: graphemes. Characters, may not represent fully human comprehensible characters, but actually, may reference bits of them sometimes, such as the following one for example: '्'. This is actually considered character. 

So if we tried to ``.char().collect::<Vec<char>>()`` the following string: "नमस्ते". We would end up with ['न', 'म', 'स', '्', 'त', 'े'] instead of this ["न", "म", "स्", "ते"].

Rust does not provide functionality to build graphemes as it can bring quite some complexity to the table. But, many crates provide such functionally. The [unicode_segmentation](https://crates.io/crates/unicode-segmentation) crate, provides tools for it, among others. 

Here a small example using it to iter through human defined characters, or, graphemes:
```rust 
for graph in "abc".graphemes() {
	println!("{graph}");
}
```
