It is recommended to check [this](../../Typing/Aliasing) out before 

Originally the orphan rule doesn't allow us to implement a type that is external to our crate, with an external trait. 

You can get around this, by simply warping our type inside a tuple struct and then, implementing a trait to the internal struct, instead of the type directly. 

The only issues with this solution, is that we must implement it for each case and variation we desire to implement with the following trait and all self methods must access the actual underlying selecting the first tuple's index (``.0``).

```rust 
use std::fmt;

//The wrapper for each implmentation case
//Almost like a monad
struct Wrapper(Vec<String>);

impl fmt::Display for Wrapper {
	//Here we can finally acess the undelying data type and implement it
	fn fmt(&self, f: fmt::Frontmattew) -> fmt::Result {
		write!(f, "[{}]", self.0.join(", "))
	}
}

```