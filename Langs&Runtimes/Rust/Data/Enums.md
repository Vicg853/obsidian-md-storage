Enums, just like structs are almost essentials when building things with Rust, when creating types and are also pretty similar. 

Enums in Rust are pretty similar their variations in other functional languages. They can be defined as a list of variations for a same type. 

They a declared like so: 
```rust
enum Drinks {
	COFFE,
	JUICE,
	WATER
}
```

Now we have a type ``Drinks``, that can be of values ``COFFE``, ``JUICE`` and ``WATER``. 
You can you use it with the double column notation, like this:
```rust
let my_drink = Message::COFFE;
```

## Compound Enums
A pretty neat feature that Enums have on Rust, is the ability to store data, of any type inside its variants.

Tu do it, we either use parenthesis (for: strings, integers, floating points, tuple structs) or brackets (for anonymous structs). 

Lets modify the above example:
```rust 
enum Drinks {
	COFFE { hot: bool, long: bool },
	JUICE(String),
	WATER
}
```

We can now insert data into it:
```rust
let my_scnd_drink = Drinks::COFFE({ hot: true, long: true });
```

## Implementations and traits 
Just like structs, Enums also accept implementations and traits. They can be declared in same way as for structs.

```rust
impl Drinks {
	fn check_juice_availabilitty() -> bool {
		//...
	}
 }
```




