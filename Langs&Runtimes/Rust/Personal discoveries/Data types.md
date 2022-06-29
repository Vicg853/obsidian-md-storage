## Tuples
##### Not iterable
With the help of stack ovflw https://stackoverflow.com/questions/57640774/is-it-possible-to-iterate-over-a-tuple. 

```rust
let x = (1, 2);

 //This is not possible
for i in x {
	println!("Int: {}", i);
}
```
