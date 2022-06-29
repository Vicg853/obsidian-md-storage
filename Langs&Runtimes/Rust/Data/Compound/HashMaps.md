HashMaps are included into Rust's STD library, they can just like structs, be compared to objects in OOP programming.

The thing about hashmaps that differs them from sturcts, is that they are closer to OOP's objects, as they aren't required to have defined types: key, values can be appended gradually and can be of any type.

Here how you define and use a HashMap using the STD library
```rust
use std::collections:HashMap;

fn main() {
	let my_hashmap = HashMap::new();

	my_hashmap.insert("MyKey".to_string(), "MyVal".to_string());
	my_hashmap.insert("MyOtherKey".to_string(), 10);
}
```

## Reading
(lets consider we are still inside ``main``'s scope)
```rust
let x = my_hashmap.entry("MyKey");
```

## Inserting without overriding
(lets consider we are still inside ``main``'s scope)
```rust
my_hashmap.entry("Msg".to_string()).or_insert("My message".to_string());
my_hashmap.entry("Msg".to_string()).or_insert("My message that wasn't written into the hash!".to_string());
```