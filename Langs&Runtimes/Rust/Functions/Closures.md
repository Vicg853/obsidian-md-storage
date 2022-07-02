Closures are a variant type of a function: they receive a set of parameters and give a certain output based on these parameters.

Closures are different than functions in the following way:
- Closures capture the scope around them: they keep track of variables and other things defined outside their own scope, while functions are limited to their own scope and arguments
- Their definition (more on that bellow)
- They can be assigned to variables and passed as arguments
- They can be one-lined
- Each of their arguments are limited to an only type definition, which can be explicitly defined or defined by the compiler, based on its first call arguments and result

The convention is, to use closures when you have a set of quick instructions to be executed in a small scope. 

## Definition
The only diference from defining a function and a closure, are the arguments surrounding characters: instead of parenthesis we use vertical pipes...
```rust 
let calc = |x, y| {
	println!("X is {} and y {}", x, y);
	x * y
}
```

#### One-lined closures
We can define a closure on one line, if the same has an only statement of expression:
```rust
let calc_1_line = |x, y| x * y;
```

#### Implicit type anotation
```rust 
let calc_typed = |x: i32, y: i32| -> i32 {
	println!("X is {} and y {}", x, y);
	x * y
}
```

## Usage
It is done in the same way as a function: ``calc(2, 3)``

## Outside scope
As said, closures keep track of their surroundings. To do it, they automatically borrow values.
But they are not limited to it, you may also borrow mutable variables and even move values into its scope.

#### Moving 
To make a closure move variables into it scope you may use the ``move`` keyword before its definition:
```rust
let y = 3;
let closure_move = move |x| x * y;

println!("Y is {}", y); 
//This can't be done anymore, as y was move into 
// 'closure_move'
```

> _Note_ that, closures that move values can't be called more than one time, as these same values can't simply be move twice. 

## Closure types
There are three main closure types, in cases where you may want to infer it:
- ``FnOnce``: a closure takes ownership of used values (they move used values into its scope), which also means that they can only be called once, as you can't get ownership of a same value twice.
- ``FnMut`` : a closure that will borrow mutable variables from it surroundings
- ``Fn``: a simple and normal closure, that immutably borrows values 