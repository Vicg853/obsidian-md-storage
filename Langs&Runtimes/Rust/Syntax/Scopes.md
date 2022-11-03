Rust scopes are pretty much the same as other languages, we just use: ``{`` (to open them) and ``}`` (to close them).

## Scope tags
You can tag scope block, they are useful for breaking or continuing with specific scopes, when they're nested. The declaration syntax is similar that with lifetimes, the difference is: it is followed by double columns and a scope statement or expression

```rust
'my_scope: {
	break 'my_scope;
}
```

## Variables
There are relations between [[Variables| variables]] and scopes: you can use them to execute complex operations so your scope becomes an expression which's return value will be assigned to the variable.
```rust
let a: u32 = {
	1
};
```