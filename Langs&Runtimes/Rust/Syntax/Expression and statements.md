With Rust, something you must keep in mind, is the expressions and statements concept. 

_An expression_: is a piece of code, that returns something.
While a _statement_: does not return anything.

We must keep close attention when doing each of them, as in Rust, as an example: using semicolon at the end of a function's expression, turns its expression into a statement. 

```rust 
fn a() - i32 {
	5 //This is an expression
}

fn b() - i32 {
	5; //Now this is a statement and this function would be of '()' return type instead
}
```

While ``let``s, ``if``s and etc keywords are statements, macros, functions, primitives are expressions.