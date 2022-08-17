Characters in Rust are the most primitive alphabetic type. Characters must be annotated with single quotes: ``'``, as opposed to ``String`` and ``&str`` types, which use double quotes. 

Also, Rust characters are four bytes and comply to the Unicode scalar values convention.

```rust
let a: char = 'A';
let b = 'B';
```

> Note that characters are not a thing in Unicode, so Rust ``char``s, although looking pretty similar, do not match with the human definition of a "character".