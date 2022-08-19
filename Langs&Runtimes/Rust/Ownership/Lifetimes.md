Generical lifetimes annotations or lifetimes, as they are commonly called, are similar to generic type annotations: they are used to represent a lifetime value, that can be compared.

They are used only with references and help you communicate with the compiler, on complex cases. 

They can be used anywhere generics can be declared.

Lifetimes, when assigned to multiple references, will have the same lifetime value as the smallest assigned variable lifetime.

## The three elision rules
In some cases, the compiler can find out lifetimes by itself. These rules are only applied in ``fn`` definition and ``impl`` blocks. For that to happen, one of these 3 rules must be applied:
1. Each reference parameter, has a one and only lifetime parameter assigned to it
2. If there is only one input lifetime parameter (at least only one reference), then all output lifetime parameters are assigned to that parameter's lifetime
3. If one of the passed parameters is a ``self`` reference, then all output lifetimes will be assigned to ``self``'s lifetime

The compiler will try to apply by itself, all of three rules for all references... But, if in any case, at the end, there are still ambiguities about one or more references' lifetimes, then, it will error.

But, if all references could get their lifetimes figured out, then, the compiler could figure things by itself, even if not rules were applied!! These rules aren't meant to be fully meet, but instead, to try to figure out each element's lifetime.

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

## Case by case

#### Functions
The above examples, show already how lifetimes work and thei specifities. 
Additionally, you must keep an eye for return type lifetimes, which is shown by example at [down here](##Smallest_lifetime_by_example).

#### Struct
```rust
struct MyStruct<'a> {
	field: &'a str
}
```

A good way to think with struct and lifetimes is: a struct, can't have a longer lifetime than of its lifetimes values.

#### Impl
If an ``impl``'s block struct requires a lifetime, then, it must define a lifetime. Apart from the specific case, lifetime definitions in ``impl``s are only required if one of the methods require them. 

Lifetime definition at ``impl``s are done just after the keyword:
```rust
impl<'a> MyStruct {
	fn one() -> u8 {
		1
	}
}
```

As for their methods, they follow the same definition properties as functions.

#### Scopes
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

Just keep an eye, not to use this lifetime keyword, to cover actual dangling reference issues, instead FIX THEM. Use ``'static`` when it is wright to use.

## Smallest lifetime by example
As said, a lifetime annotation will have the same value as the smaller lifetime value of all its assigned references.

Consider this example from the Rust book
```rust
fn longest<'a>(x: &'a str, y: &'a str) -> &'a str { 
	if x.len() > y.len() { x } else { y } 
}
```

Here, if ``x`` has a smaller lifetime than ``y``, ``'a`` will have the same lifetime value as ``x`` and vice versa. That later reflect on the function's result: the returned slice will have the same lifetime as the smaller inputted lifetime.

Which means that this following example, that uses the function defined above, will not compile:
```rust
fn main() {
    let string1 = String::from("long string is long");
    let result;
    {
        let string2 = String::from("xyz");
        result = longest(string1.as_str(), string2.as_str());
    }
    println!("The longest string is {}", result);
}
```

> As said, ``'a`` is assigned to the smallest lifetime. In this case, ``string2``'s lifetime. Which means the value assigned to ``result`` will share this value. Therefore, when used on the outer scope, will cause the borrow checker to error, as ``stirng2`` does not life long enough. 

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