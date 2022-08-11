## Char and string literals

#### Raw string literals
Raw string literals, are useful when using special ``"`` characters inside a string, e.g.: when writing a JSON strings.

Consider the following case, that would probably error, as we use ``"`` inside our string:
```rust
let my_json = "
	"a": 1,
	"b": 1,
	"c": [
		"abc",
		"efg"
	]
"; 
```

We may solve this, using raw string literals... We declare a raw string literal, by prefixing our string with an ``r`` followed by N quantity of ``#``s and an  opening ``"``. To close our raw string literal we use a ``"`` followed by the same N number of ``#`` at the end.


Now, this works:
```rust
let my_json = r#"
	"a": 1,
	"b": 1,
	"c": [
		"abc",
		"efg"
	]
"#;

//And this also works 
let my_complex_string = r##"This, will not close: "# It will only close here -> "##
```


