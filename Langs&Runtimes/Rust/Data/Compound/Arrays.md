Arrays in Rust, are like most other programming languages arrays. They differ to some language are in their fixed length and only type characteristics. Arrays are stored on the memory's stack. Just like tuples, they aren't modifiable by themselves, but its underlying data can be mutated.

If you need variable lengths, you should use vectors. 

They are useful, when defining a known size list of data. 

```rust
let my_arr = [10, 20, 30];
```

To access values in arrays, just use the bracket syntax:
```rust
let my_int = my_array[1];
```

#### Out of range access
When trying to access elements, that don't exist in an array (e.g. with an user input based index), at runtime, Rust will panic.  

This ensures memory safety, preventing the program from using/accessing invalid memory. 

## Ease of use and type definition
You may create a bulk array definition. It is done by surrounding two values with brackets, which are separated by de semi column. The first element corresponds to the value which will be defined in bulk and the second one, to the number of iterations that should be created.
```rust
let my_range_arr = [2; 15];

//This will create an array of only the "2" value, with a length of 15.
```

Note that, this syntax is pretty similar to arrays type definitions. Rust will obviously panic if you mistype one of both, but keep an eye for this type of confusion.

The different from bulk-definition and type definitions is that the first element corresponds to the data type and the second one, to the array's length.
```rust
let a: [i32; 5] = [1, 2, 3, 4, 5];
```