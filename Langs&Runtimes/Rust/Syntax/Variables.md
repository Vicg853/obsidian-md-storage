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

#### Shadowing
One can also use the called "shadowing" method, where you redefine a whole variable, by reusing his name, on the same scope and even by modifying its type.
```rust
let d = 10;
let d: String =  String::from("d")
```

Note that, just like is written in the Rust book: "the second variable overshadows the first, taking any uses of the variable name to itself until either it itself is shadowed or the scope ends". 
So we may retrieve old values at the end of a scope for example:

```rust
fn main() {
    let x = 5;

    let x = x + 1;
    {
        let x = x * 2;
        println!("The value of x in the inner scope is: {x}");
    }
    println!("The value of x is: {x}");
}
```

The above code will result in: 
```
The value of x in the inner scope is: 12
The value of x is: 6
```
Because the shadowing here ``let x = x * 2;`` will only endure until the end of the inner ``{ }`` scope.

## Const ``const``
Differently than ``let``, ``const``s are craved into the app's binary and can't be assigned at runtime. Constants talk by themselves, they are constant and _can't_ be re-asigned or mutable, in any way at any point. 

They also MUST be ALWAYS followed by a type annotation.

```rust
const a: String = String::from("A");
const b: u32 = 10;
```

They can also be defined either under a function scope's or the global program's scopes (at a file's root), making them useful for defining variables used across the whole program and shouldn't submit to changes, e.g. the speed of light.

To be more specific about the no runtime assignement rule, ``const``s can't be assigned to:
- I/O input
- Function responses or futures
- User input
- Other variables that aren't constants (e.g.: ``let``s assigned by user input, or mut, or shadowed)

Here is a more in depth list of constant evaluation compatible expressions: https://doc.rust-lang.org/stable/reference/const_eval.html.