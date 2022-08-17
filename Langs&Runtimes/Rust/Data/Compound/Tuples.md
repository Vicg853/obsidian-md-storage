Tuples are fixed length lists of values. They are similar to arrays, with the peculiarity of supporting different data types. 

Apart from that, they have fixed size and are represented, aren't mutable themselves (only underlying data is) and already defined data types, must comply to previously defined types.

```rust
let my_tupl = ("player", 20);
```

## Accessing data
There are two ways to access aa tuple's data:
- De-structuring with pattern matching:
```rust
let (player_name, player_lives) = my_tupl;
```
- Dot notation:
```rust
let player_name = my_tupl.0;
```

> When accessing out of range values, Rust compiler will panic at build time.

## The ``unit`` tuple type
A tuple, with no items in it, is called an "unit". Its value and type are both written in the following format: ``()``. They represent empty value &/or return type.