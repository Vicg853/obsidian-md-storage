The match expression is used mainly with Enums. 

The match operator compares the inputted data to defined cases. We start by defining the keyword followed by the desired value. Then, on each following (inside its scope) line we handle the cases by defining the case value and the resulting function, return, etc, on the right of an arrow ``=>``.

``match``es are declared like so:
```rust 
// Consider the following enum and var
//enum Section {
//	One,
//	Two
//}
//let section = Section::One;

match section {
	Section::One => {
		println!("Option one");
	},
	Section::Two => 2
}
```

Matches are exhaustive, that is: all possibilities MUST be handled. 
In a case of innumerable variants we may use the underscore ``_`` to handle all non handled cases by default.

```rust
enum SectionSecondType {
	One,
	Two,
	Three
}

match section {
	Section::One => {
		println!("Option one");
	},
	_ => 0  //Both `Two` and `Three` variants will be handled here
}
```

## Enum variant values
In the case an Enum has a variant built into it, you may also handle it inside a match. You do it by defining a variable with the variant, just as a function's inner argument:
```rust
enum SectionThirdType {
	One,
	Two(i8)
}

let section2 = SectionThirdType::Two(2);

match section2 {
	SectionThirdType::One => {
		println!("Option one");
	},
	SectionThirdType::Two(sub_section) => {
		println!("Section two with sub section {}", sub_section);
	}
}
```

> _Abstraction:_ We could say that when checking the above case, Rust tries to create a variable from the SectionThirdType::Two variant. If it does not succeed (the value var can be defined), it goes the follows on with matching, but if it does succeed, it defined the value just as a function inner argument, that can be used on the right side of the =>

## Match and borrowing
When passing the match value result to a case, you may want sometimes not to move the value, but only borrow if. For it, you may use the ``ref`` keyword, before the defined variable

```rust
match a {
	Some(ref val) => println!("Value exists and is: {}", a),
	_ => println!("Value does not exist")
}
```