Patterns are used to describe the shape of data we are working with, that can be matched against values.

Patterns are useful for de-structuring data, for easier usage.

## Irrefutable and refutable patterns  
There are two pattern types in Rust, the meaning and name of each pattern are:
- Irrefutable patterns: as their name says, they can't be refuted. That is, data MUST match it;
- Refutable patterns: as their name says, they may be refuted. That is, data isn't required to match it;

Not every case can accept both. 
Some cases ONLY accept irrefutable patterns:
- function parameters;
- let statements;
- for loops;
If these rules aren't followed, Rust will panic at compile time.

Differently, in cases where irrefutable patterns aren't required, Rust won't panic at compile time and will only warn you about it, as they are probably useless.

## Syntax
#### Literals
You may match against literal patterns. 
```rust
match a {
	1 => /*... */,
	2 => /*... */
}
```

#### Named variables
These usually don't have any constrains, as raw variables can be usually matched to anything.
```rust
match b {
	c => /*... */,
}
```

#### multiple patterns
We may use operators to define multiple patterns to match data. For example, the or opperator
```rust
match a {
	1 | 2 => /*... */
}
```

#### Ranges
We can use ranges, to scope many data into many pattern matches. Note that, this only works with characters and numeric values. They are done with the range operator ``..``:
```rust
match c {
	1..4 => /*... */,
	4..=6 => /*... */,
	_
} 
```

#### Any
These are used when we wan't to match to any type, without declaring variables. For that the catch all syntax ``_`` exists. This works when working with matches, the option enum, if statements, ...:
```rust
match c {
	_ => /*... */
}
```

#### Guards
Sometimes, matches themselves might not be enough, for that we may use guards. They are defined after the main match expression, with an ``if`` statement and its condition.
```rust
match my_enum_val {
	MyEnum::String(my_string) if my_strin == "Hello World" => /*... */,
	_ => /*... */
}
```

#### De-sctructuing patterns
De-structuring patterns can be used along structs, enums, tuples and references. They can be used to at the same time: easily access and creating narrower patterns.

- _Structs_:
	With structs it is done similarly with when we define a variable based of it. The both defines de-structured data and assures that the data matches the struct's type
	```rust
	struct Point {
		x: u32,
		y: u32
	}

	let a = Point { x: 1, y: 2 };
	let Point { x, y } = a;	
	```
	We may also  de-structure data, into differently named variables. For that we use column a column after the defined field, followed by the de-structuree variable name. Consider the above example:
	```rust
	let Point { x: my_x, y: my_y } = a;
	```

	We can also use it with the ``match`` keyword in a very special way, where we can ensure a field matches a pattern in itself. For that we define the value after the column. Consider the above examples
	```rust
	match a {
		Point { x, y: 0 } => /*...*/,
		Point { x, y: 1 } => /*...*/,
		_ => /*...*/
	}
	```
- _Tuples_:
	We may also de-structure tuples. This is done similarly to struct, the only diference, we simply use both opening and closing parenthesis, plus values, thats it:
	```rust
	let a = (1, 2);
	let (x, y) = a;
	```
- _Enums_:
	For enums, we basically, use the respective variant's name, optionally followed by the underlying data's type de-structuring procedure. For scalar data, we simply define it between parenthesis:
	```rust
	match my_var {
		MyEnum::Normal => /*...*/,
		MyEnum::Tuple(x, y) => /*...*/,
		MyEnum::Scalar(my_string) => /*...*/,
		MyEnum::Struct { x, y } => /*...*/,
		MyEnum::Scalar(my_string) => /*...*/,
	}
	```

#### De-structuring & Ignoring
There are two ways of ignoring certain data and only match de-structure based of certain data patterns:
- The ``_`` also serves as an ignore syntax. It allows you to only define data that you want to and ignored whomever is "assigned" as ``_``.
	```rust
	let a = (1, 2, 3);

	let (one, _, _) = a;
	```
- The range ``..`` operator, which allows you to ignore any other data, that is not explcitly defined. Consider the example above:
	```rust
	let (one, ..) = a;
	```

#### De-structuring & Bindings
Sometimes, when de-structuring, we may want to both: define a custom variable out of the underlying data and specify detailed pattern using ranges, etc.  By using the ``@`` operator, we may do it. 
We define the custom variable as usual, followed by an ``@``, which is followed by our condition in itself:
```rust
match my_enum_val {
	MyEnum::Struct { x: my_xm @ 1..=5, .. } => /*... */,
	_ => /*... */
}
```

## Expressions examples
Here are some patterns examples.

#### If let
If let patterns, are usually used to conditionally proceed with something, based of a pattern match. 
One of the most used Rust if let patterns, are with the Option enum Some and None variant's.

```rust
let x: Option<u32> = None;
if Some(num) = x {
	//...
} else {
	//...
}
```

Here, if ``x`` can be matched to ``Some(num)`` (aka it can be assigned to it), then Rust will proceed to the if's inner scope, with the adition of the defined variable.  
Otherwise, Rust will proceed with the else's scope.

#### while & For
We can do almost the same thing as with the if let statement, with inside while loops.
We can, based of an iterator, while its data is assignable to something, execute scoped code.

```rust
let mut a = vec![1, 2, 3];

while let Some(my_num) = a.pop() {
	//...
}
```

Here, Rust will iterate through ``a``, and while it does not reach its end, it will assign the underlying value to ``my_num`` (as it exists and is assignable) and run the scope code. That happens until we reach ``a``'s end, where the value will be of ``None``, which means ``Some(my_num)`` can't be assigned, hence the stop.

It can be similarly be done to a ``for`` loop. Where for each element in a inerrable component, Rust will define and run scoped elements for the matched pattern.

#### let
The most mainstream pattern, is done with let statements. 
The most basis one being the ``let PATTERN = EXPRESSION;`` format:
```rust
let x = 6;
```

Here we declaring matching  that ``let``'s data to a a``x`` pattern, which means, to anything.

But we can also constrain things a little bit more, by using aa tuple pattern for example.
```rust
let (x, y) = (1, 2);
```

> **Remember** that, let statements only accept irrefutable patterns, so assigning ``let`` as to ``Some`` is forbidden. 
> **Unless** if it specifically consists of an ``if let`` statement, as seen above

#### functions
Functions can similarly require argument patterns, pretty much in the same as it is done by ``let`` statements.

```rust
fn a(&(x, y): &(u32, u32)) -> u32 {
	//...
}
```

Now when calling the function we must pass an argument that matches the above pattern.
```rust
let tupl = (10, 20);
a(&tupl);
```