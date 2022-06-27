See [modules](./Rust_modules) before reading this.

A same file may contain multiple different modules. But in some cases, we may want to split things in different files to make readability easier. To do it, we simply use a specific but simple file structure:

#### Module file
An ``.rs`` file, named in a certain way inside the source directory, that exports a ``pub`` resource, will be considered a module. It must be imported into scope using the ``mod`` keyword followed by the file name (that is also the module's name).

_my_mod.rs_
```rust
pub fn a() {
	//...
}
```

_main.rs_
```rust
mod my_mod;

fn main() {
	a();
}
```

> _We can also_ name a folder with the same name, containing a mod.rs file

#### Module sub modules
To create a module sub modules, we do it in a similar way, following an only rule: children must be placed inside a folder, that is name the same way as the module definition file, or the folder must contain a ``main.rs`` file, with the module root's content.

Then we must bring the sub module into the root scope's, using the ``pub mod`` keywords.

_my_mod/sub_mod.rs_
```rust
pub fn b() {
	//...
}
```

_my_mod.rs_
```rust
pub mod sub_mod;

pub fn a() {
	//...
}
```

_main.rs_
```rust
mod my_mod;

fn main() {
	my_mod::a();
	my_mod::b();
}
```