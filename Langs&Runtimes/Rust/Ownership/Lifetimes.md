Generical lifetimes annotations or lifetimes, as they are commonly called, are similar to generic type annotations: they are used to represent a lifetime value, that can be compared.

They are used only with references and help you communicate with the compiler, on complex cases. 

They can be used anywhere generics can be declared.

## The three elision rules
In some cases, the compiler can find out lifetimes by itself. For that to happen, one of these 3 rules must be applied:
1. Each reference parameter, has a one and only lifetime parameter assigned to it
2. If there is only one input lifetime parameter (only one reference), then all output lifetime parameters are assigned to that parameter's lifetime
3. If one of the passed parameters is a ``self`` reference, then all output lifetimes will be assigned to ``self``'s lifetime

## Usage
You can use your defined lifetime in the following way:
- With a reference: ``&'`` + the lifetime's name (no space or anything) + space + your type definition
	```rust
	fn my_func<'a>(arg: &'a i32) { }
	```
- With a mutable reference: ``&' mut`` + the lifetime's name (no space or anything) + space + your type definition
	```rust
	fn my_func<'a>(arg: &'a mut i32) { }
	```

## Empty scopes
You can also define lifetime on empty scopes
```rust
'a: {
	let z: &'b i32;
}
```

## Static lifetimes
A static lifetime is an annotation used to denote that a variable's/parameter's lifetime has a runtime lifetime duration.

For example, ``str`` literals automatically have a static lifetime, as they are stored in the binary. 

To assign a static lifetime, you just need to replace the lifetime's annotation name by the ``static`` keyword (after the apostrophe).

```rust
let a: &'static;
```

## Lifetimes by example
This is useful when you are returning a passed in parameter, as it explains to the compiler that you are returning a reference, to an outside variable that has a longer lifetime than the function's lifetime. 
Now, the compiler will know that it must check for a variable's lifetime instead of the function's lifetime. 

Consider this example:
```rust
fn main() {
	let my_string = String::from("A");

	let res = my_func(my_string.to_str());
	println!("Res is: {}", res);
}

fn my_func<'a>(arg: &'a str) -> &'a str {
	arg
}
```
> Now the compiler knows that it must check for the passed "arg" parameter lifetime, as the function returns a lifetime that has same longevity as the "arg"'s one. 