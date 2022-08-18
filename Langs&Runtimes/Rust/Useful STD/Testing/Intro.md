Test in Rust are simple annotated functions, that are compiled into a binary, along your program during a test run request. This program is than ran. 

Each test, is invoked inside a new thread, and this is how Rust evaluates tests: when a thread dies (panics) with no success result, Rust knows, this test failed.

## Basic declaration
To declare test, the convention is to do it under a new module called test. This module should be annotated with the ``#[cfg]`` macro and ``test`` as a parameter, which will prevent test from being included to release binaries. 

Each test function, must be annotated with the ``#[test]`` macro. Rust will run and evalute these function at test runtime.

```rust
#[cfg(test)]
mod test {
	#[test]
	fn two_plus_two() {
		let added = 2 + 2;
		assert_eq(added, 4);
	}
}
```

## Output
A set of informations will be outputted to the CLI during a test:
- The number of test being ran, e.g.: 'running 1 test'
- Each test name, module and result, e.g.: 'test tests::it_works ... ok'
- A test summary, e.g.: 'test result: ok. 1 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.00s'. Which is composed of (respectively): 
	- The number of passed tests
	- The number of failed test
	- The number of ignored test, which are specified with the test ignore cargo flag
	- The number of benchmark test runs
	- And the number of filtered test, which usually are conditional test, based of environment circumstances, such as different OSs
- And finally doc test results with its own summary. Yes, Rust test documented code. Discover more about it [here](https://doc.rust-lang.org/stable/book/ch14-02-publishing-to-crates-io.html#making-useful-documentation-comments)

