Tuples are fixed length lists of values. You can think of them as related but different data types arrays.

```rust
let my_tupl = ("player", 20);
```

There are two ways to access aa tuple's data:
- Destructuring:
```rust
let (player_name, player_lives) = my_tupl;
```
- Dot notation:
```rust
let player_name = my_tupl.0;
```

> When accessing out of range values, Rust compiler will panic at build time.