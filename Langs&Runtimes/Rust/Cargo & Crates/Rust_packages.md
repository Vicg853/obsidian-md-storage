Rust packages can be explained as isolated groups of code, containing called ``crates``, that create another level of isolation. They are similar to Node's packages....

Rust packages have some small conventions and rules that should be followed. But first, what are the different packages crate types:
- Binary crates, that by convention are composed of a  ``main.rs`` file in the source folder
- Library crates, that by convention are composed of a ``lib.rs`` file in the source folder

The main rules are: 
- A packages must contain a crate
- A rust packages/package, can contain none or only one library crate.
- A rust packages can contain one or more binary crates

Some conventions are:
- The already  mentioned file naming convention (``main.rs`` creates a binary crate withing the package's name and ``lib.rs`` crates a library crate within the package's name)
- Secondary binaries are defined under ``src/bin``

To define usable code inside packages, we use the called modules, defined by the ``mod`` keyword and followed by their naming. More on them [here](./Rust_modules).

## Using crates & modules
Accessing a crate is pretty similar to routing through files on a computer. Crates are a organized in a tree like architecture, with parent and child modules (``mod``) .

To access the package's absolute path we use the ``crate`` keyword.
As for relative paths and the parent/child modules we simply use their definition names.
They should be all separated by double columns.

```rust
//Absolute
crate::my_mod::my_func();

//Relative
my_mod::my_func();
```


