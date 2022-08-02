The turbo fish syntax (a.k.a. ``::<`` + Type + ``>``) is used to specify a generic's concrete type at a method/function call. 

It allow us in some cases to reduce code length, mitigating type annotations, or assign middle statement types without assigning it as the final one, and even when types can't be figured out at compile time, thus forcing manual type inference 

It follows the format of two angled brackets surrounding a concrete type and is usually state after double columns. 

```rust
let a = HashMap::<String, i32>::new();

let a = Vec::new().iter().collect::<Vec<&str>>();
```