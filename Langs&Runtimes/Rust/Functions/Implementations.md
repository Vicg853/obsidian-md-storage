First check out [structs](../Data/Structs).

Structs are pretty useful to create data, but they are not that great alone. And that's when implementations come into place: we use them to add extensions to our struct, providing built-in functionalities to it. We call these: *  *methods*  *

Let's discover more about methods/impl in Rust....

...but first, we need a struct:
```rust
struct Quad {
	width: u64,
	height: u64
}
```

Then, lets add an initial empty implementation were we will add our methods. Note that the definition is composed of the ``impl`` keyword, followed the desired Struct's name.
```rust
impl Quad { 
  //...
}
```

## Simple Methods
As said, methods are functions. The straightforward version of methods always receive a reference to itself as a first argument, this way, methods will be tied to a Struct's instance.
```rust
impl Quad { 
	fn area(&self) -> u64 { //<-- note the &self notation that determines this function is a tied method
		self.width * self.height
	}
}
```

You can then use a methods on your instances:
```rust
let rectangle = Quad {
	width: 30,
	height: 20,
}
println!("Teh rectangle's are corresponds to: {}", rectangle.area())
```

## Associate methods
Differently than simple methods, associative methods are not linked a Struct's instance. That means, they are not defined inside an instance, and can't be used. An associative function NEVER receives a &self argument. 
They can be used to create instances for example. You can think of them as raw struct simple methods:
```rust
impl Quad {
	fn new_square(size: u64) -> Rectangle { //<-- note the lack of the &self notation that determines this function is an associate function
		Rectangle {
			width: size,
			height: size
		}
	}
}
```

They are used the following way: 
```rust
let mySquare = Quad::new_square(40);

//You cant to the following
// mySquare.new_square()
// this method is not avaible inside mySquare, as it is an instance.
```
