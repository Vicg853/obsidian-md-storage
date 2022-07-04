In some cases, importing modules can get hard/annoying/messy as more and more modules, with deeper nesting get created. 

To fix that, we may uses the ``use`` keyword. The use keyword will allow us to shorten modules usage definitions, by bringing them or their resources into scope. Rust brings into scope the last definition referenced after its keyword.

#### no use
```rust
fn main() {
	crate::my_mod::my_sub_mod::my_other_mod::my_func();
	crate::my_mod::my_sub_mod::my_other_mod::my_scnd_func()
}
```

#### With use
```rust
use crate::my_mod::my_sub_mod::my_other_mod;
use crate::my_mod::my_sub_mod::my_other_mod::my_scnd_func;

//Now my_other_mod and my_scnd_func() are in scope
fn main() {
	my_other_mod::my_func();
	my_scnd_func();
}
```

## Nested use imports
We can also import multiple module resources using ``{}`` anotator after the module's name  and defining which resources are to be imported. With that we can reduce definition boilerplate by merging imports with a common path.

```rust
use crate::my_mod::my_sub_mod::my_other_mod::{my_func, my_scnd_func};
```

## Renaming with ``as``
We can also rename some resources in scope, for cases where we have resources named similarly.
For that we use the ``as`` keyword after the module's or resource's in scope ``use`` definition.

```rust
use crate::my_mod::my_sub_mod::my_other_mod as MyMod;

//Now my_other_mod is defined in scope as MyMod
fn main() {
	MyMod::my_func();
}
```

## Exporting and importing to external file 
The ``use`` keyword is also useful for two other things:

#### external CRATE access grant
Sharing a crate's module to other ones. For that, in our root file (either a bin or lib crate root file) we bring into scope the desired path with ``use``, we then mark this import as public with the ``pub`` keyword.

```rust
pub use my_mod::my_sub_mod::my_other_mod as MyMod
```

#### external CRATE import
In the same way we may import internal modules, we also may import external modules from other crates. For that we just name the crate at start of our use definition and then we use the same rules as for internal modules, to access this crate's modules.

```rust
use MyOtherCrate::my_module;
```

## Glob pattern and self import
Two other features come with nested imports:
- The glob pattern using the ``*``, that allow us to bring all nested modules from a path
	```rust
	use MyOtherCrate::*;
	```
- The ``self`` import, that allows you to import child resources along with the parent module in itself
	```rust
	use MyOtherCrate::{self, my_module};
	```

## With data types
You may also use ``use`` (haha) with other data types. They allow you to bring their child elements into scope. 

Example with an enum:
```rust
enum my_enum {
	A,
	B
}

use my_enum:{A, B};
//Now A and B can be used directly as they are in scope
```