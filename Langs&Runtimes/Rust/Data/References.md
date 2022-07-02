Something that helps us a when working with Rust's ownership systems are _references_ (usually called as borrowing too). 
References can be used when we want to access data, without taking ownership for it. 

To create a reference, we use the ``&`` symbol before the String type and variable usage. 

(consider the example above)
```rust 
fn get_string_length(string: &String) -> usize {
	let length = string.len();

	length
}

fn other_func() {
	let my_second_string = String::from("Coding a dinossaur!");

	let second_strg_length = get_string_lenth(my_second_string);

	println!("My second string is: {}, and it has a length of {}", 
		my_second_string,  //This is still accessible
		second_strg_length;
}
```

## Mutable Refs
What if we need to modify data? For that we have mutable references, that are defined in a similar way, only needing to use ``&mut`` instead of only ``&``.

```rust
let mut x = String::from("Hi!");
let y = &mut x;

y.push_str(" How are you doing?");
```

## References and ownership 
You must take care when using references. A set of rules provide memory safety when using them, so take a look [here](Ownership.md).