## Let: ``let``
The ``let`` variable can be compared to javscript's ``let``. 

In Rust, they are usually the most used during your progress, they are usually assigned and used at runtime, but are not limited to it, and can be static depending on the way data is defined. They do not require a type definition after its keyword.

```rust
let a = "a".to_string();
let b: u32 = 10;
```

This type of variable, can be defined as a mutable, that is, its value can be modified. To do it you must use the ``mut`` keyword after the ``let`` keyword. Note that in this case, types are required.

```rust
let mut c: u32 = 10;

c = 20;
```

Although, one can use the shadowing characteristic, where you basically redefine a whole variable, by reusing his name, on the same scope. In this case, type can even be modified.

```rust
let d = 10;
let d: String =  String::from("d")
```

## Const ``const``
Differently than ``let``, ``const``s are craved into the app's binary and can't be assigned at runtime. Constants talk by themselves, they are constant and be re-asigned or mutable, in any way. 

They also MUST be ALWAYS followed by a type annotation.

```rust
const a: String = String::from("A");
const b: u32 = 10;
```

To be more specific about the no runtime assignement rule, ``const``s can't be assigned to:
- I/O input
- Function responses or futures
- User input
- Other variables that aren't constants (e.g.: ``let``s assigned by user input, or mut, or shadowed)
