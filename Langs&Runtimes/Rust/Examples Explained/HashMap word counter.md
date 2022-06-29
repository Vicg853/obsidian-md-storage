[Let's Get Rusty Video](https://youtu.be/Zs-pS-egQSs?t=1323)

```rust
let text = "hello world wonderfull world";

let mut map = HashMap::new();

for word in text.split_whitespace() {
	let count = map.entry(word).or_insert(0);
	*count += 1;
}

println!("{:?}", map);
```

In the first ``for``'s line, we use the method ``split_whitespace()`` that will split the string on whitespaces and return an array of string slices.

2nd ``for``'s line: We then check if the current string slice exist as an entry inside ``map``. If it exists, it returns a reference to its current value. If it does not exist we will insert a value 0 with the current word as a key. 

3rd ``for``'s line: Now, we user the deference expression to then add 1 to the value with the current word as key inside map. 

We finally print map which will result in ``{"hello": 1, "world": 2, "wonderfull": 1}``