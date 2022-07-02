Vectors are similar to arrays and tuples:
- They are compound 
- Their values are indexed instead of having a key/value structure as structs
- Just like arrays they accept an only data type (although you can store structs and Enums for more broader cases)
- You read data from them just as it is done with arrays
- If values are not set at declaration them types must be inferred 

The key diference being that vectors are of variable sizing.

## Declaration
You can declare vectors in two ways with Rust:

##### The ``vec![]`` macro 
```rust
let my_vector = vec![1, 2, 3];
```

##### The STD library ``Vec`` 
```rust
let my_vector2: Vec<i32> = Vec::new();
```

## Reading
Just as in arrays, we use ``[i]`` to read data inside a vector.

The catch is that, vectors have variable sizes, which can cause invalid indexe reads as data my not exist yet/anymore at this certain index, causing an out of bound error. 
On top of that, as its' sizes are variable, there is no way for the compiler to check/handle this cases, which could probably wind-up could wind up in runtime out of bound errors.

Because of that, we must handle these reads by ourselves. We can do it by simply checking the value's existence or by using the ``.get()`` method, which ensures a higher level of security by returning an ``Option<>`` enum (more about that [here](../../Syntax/Option_Enum)), forcing us to handle these cases.
But handling this, is not limited by both...

```rust
if let Some(el) = my_vector[4] {
	println!("The choosen index is of value: {}.", el)
} else {
	println!("No such index!")
}

match my_vector.get(4) {
	Some(el) => println!("The choosen index is of value: {}.", el),
	None => println!("No such index!")
}
```

## Append data
To append data after initialization to a vector, you may use the ``.push`` method among other methods.
```rust
my_vector2.push(1, 2, 3, 4);
```

## References 
You can just like with other data types, create references, following the same rules. 

Remember that, you can only have an only mutable references or many immutable references inside a "virtual" scope (as explained and abstracted [here](Ownership.md)).

Under the hood, this is justified by the fact that vectors are stored on the heap. When mutating a vector's value and causing it to shrink/grow, this memory part is reallocated to a different address, causing the reference to point to now, an invalid address.






