Macros in Rust, are components that are typically called similarly to functions, but have a very different behaviour. 

Macros run at compile time, may compose a wide range of non specified arguments and generate code when ran. 

This allows us to narrow things down, what could take lines of code, intro smaller lines but just declaring what is needed. They also allow you to introduce syntax that Rust originally does not provide (e.g.: json syntax, just like serde's crate ``json!`` macro).

The problem with them, is that they can be quite are hard to understand and maintain, but can be a great tool when used to them.

#### Macro types
There are two different macro types: [procedural macros](Langs&Runtimes/Rust/Functions/Macros/Procedural/Intro.md) and [declarative macros](./Declarative). 