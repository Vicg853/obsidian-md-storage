Rust loops also have very similar syntax to other languages.

## Basic ``Loop``
Loop is probably the most different from other languages, but only for naming, the remaining are pretty common. It can be compared to Arduino's C++ ``loop()`` function.
```rust
loop {
	// Run your code

	break; //Stop execution
}
```

To return a inner scope value from a loop, we can pass it to the ``break`` statement.
```rust
let count = 0;
let x = loop {
   count += 1;
   if count == 5 {
	   break count;
	}
}
```

#### ``loop`` Tags
You may add a tag to your loop, for both readability and practical usage: you can use a label, to specify which loop must be broken in nested loops.

Label are declared using a ``'`` followed by the tag name and a double column. Then we simply declare the loop itself.

```rust 
'my_loop_label: loop {
	
	loop {
		if true {
			break 'my_loop_label; //This will break the outer loop
		}
		break; //This would brake the inner loop
	}
}
```

## While 
Very similar to other langs
```rust 
let a = 5;
while a != 0 {
	a -= 1;
}
```

## For
Also very similar to other langs. There are to methods to iterate using ``for``:
- Using a list's iter method:
	```rust 
	let a = [0, 1, 2];

	for i in a.iter() {
		println!("I equals to {}", i);
	}
	```
- Using the Rust's standard library range type:
	```rust
	for i in 1..5 {
		println!("I equals to {}", i);
	}
	```

When using for we can also use the ``in`` keyword to iterate over arrays, 

