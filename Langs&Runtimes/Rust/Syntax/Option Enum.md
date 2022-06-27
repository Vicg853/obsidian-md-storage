The option Enum, is one of your most important Rust Enums, it is built-in by default and included by default in the scope (without even having to use the ``Option`` keyword beforehand). That's why an entire page is dedicated to it and not included along the [Enum](../Data/Enums) page. 

## Intro
In _Rust ``null`` values doesn't exist_, a _variable_ is _either defined or not_. That's when the option struct gets in stage:

```rust
enum Option<T> { //Learn more about this T under the generics page. But for the time being, think of it as a value with ANY type.
	Some(T), 
	None
}
```

When a value is possibly undefined, we wrap it with the ``Option`` Enum. When doing that, the compiler will force us to handle the none variant of the value and give us access to it through the Some variant, as it is a compound Enum containing any value passed to it.   

To use it with variables, we just wrap its value around the ``Some()`` variant directly or we define it as ``None`` from the ground up.

Using it with a variable:
```rust
let my_var = Some(5);

let undef: Option<i32> = None;
```

> _Note_ that for the ``None`` variant, we are required to define its type, as the variable is still undefined and Rust can't define it by itself.

## Match expression and the Option Enum
(Check out the Match Expr before proceeding) 
We may use the ``match`` expression to handle the Option Enum. We do it just like any other Enum match, with Some as a compound match function. 

```rust
match some_value {
	Some(10) => println!("10!"),
	None => println!("Not def")
}
```

## If/else and the Option Enum
Or we may use the if/else operators to handle it. For that we declare a some inside our if condition and compare it to the desired optional value.

```rust
if let Some(3) = some_value {
	println!("three!");
} else {
	println!("Not def");
}
```


## Built-in implementations
Rust options have some built-in methods, to help with optional values handling. 

Here are some of them:
##### ``unwrap_or()``  
This method, will either use the defined value or fallback into a default value. 

