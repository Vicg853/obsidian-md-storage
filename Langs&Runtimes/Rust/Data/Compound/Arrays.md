Arrays in Rust, are like most other programming languages arrays. Maybe the main diference to some language are: fixed length and only type.

```rust
let my_arr = [10, 20, 30];
```

An alternative to arrays in Rust are vectors: vectors do not have fixed lengths.

You can create huge arrays with ease too. Just use the semi column for it:
```rust
let my_range_arr = [2; 15];

//This will create an array of only the "2" value, with a length of 15.
```

To access values in arrays, just use the bracket syntax:
```rust
let my_int = my_array[1];
```