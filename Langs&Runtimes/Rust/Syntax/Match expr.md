The match expression is used mainly with Enums. 

It is almost like an iterator, that receives a value and copares it to defined cases in its scopes, proceeding then with the action defined for this specific action. 

``Match``es are declared like so:
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
In the case an Enum has a variant built into it, you may also handle it inside a match, by using parenthesis, just as if we were using function arguments:
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

