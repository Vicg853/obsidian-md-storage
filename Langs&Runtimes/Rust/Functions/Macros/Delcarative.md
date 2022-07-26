Declarative macros have a similar syntax to the ``match`` expression and they are under current redesign, meaning they will probably be deprecated in the future.

They are declared by first using the ``macro_rule!`` keyword followed by the macro's desired name and curly brackets.

Then inside it, we declare something similar to a match's expression arm: a pattern between parenthesis that will tell Rust about the syntax pattern that should be used for declaration and then the respective generation code between curly brackets again.

Also, on top of the declaration we must use the state our macro with ``#[macro_export]``, in case we want to export it.

## Declaration by example
```rust
#[macro_export]
macro_rules! mini_vec { //Initial definition 
	( $( $x:expr ),* ) => { //Match expression 
		let mut temp_vec = Vec::new(); //Underlying generated code here
		$(                             //Also here
			temp_vec.push($x);          //And here
		)*                             //... here
		temp_vec                       //And finaly here
	}
}
```

Now when using the ``mini_vec!`` macro, the following stated code will be generated at compile time.

## Multiple matches
As said, declarative macros have a slightly similar syntax to match expressions in their inner syntax, and that is no different for some of its inner workings: you can declare multiple expressions matches, that could end up into different generation. 

```rust
macro_rules! my_macro {
    () => { 0 };
    ($x) => { $x };
}
```

## Matching expressions
As seen in the example above, macros can be quite complicated, mostly the matching expressions at declaration and in the middle of the code. 

Here is a small resource with match expressions: https://veykril.github.io/tlborm/decl-macros/minutiae/fragment-specifiers.html.
