Although tests are important, if developers, don't comme to a conclusion in a certain testing pattern, they can become nightmares, that probably could introduce even more problems.

Hopefully, testing in Rust is quite easy and there a set of rules, that still give you the liberty of do it your own way, but in a way that test will comply with each other.

## Unit testing
Unit testing is the practice of testing small bits of code, such as, a function, or method. In Rust, the convention states that we should write unit tests, in a sub-module called ``test``, within the current tested code's module.

This module should be annotated with the ``#[cfg(test)]`` macro, which states that this module should be used for test and should be omitted from release builds.

```rust 
fn give_me_one() -> u8 {
	1
}

#[cfg(test)]
mod test {
	#[test]
	fn test_give_me_one() {
		assert_eq!(give_me_one(), 1);
	}
}
```

> Also note that, our tested function is private. Remember that: _child modules, always have access to a parent's private resources_? That's why, the ``test`` module is a submodule, so it has access to ``give_me_one()``.

## Integration test
Integration test are supposed to see our code from a further point of view, testing it as a group instead of small parts. They are useful when integrating different libraries/library parts together (just as the name says) and ensure they behave correctly when assembled.

To create integration tests in Rust, we simply create a ``test`` folder in our project's root and files with ``#[test]`` annotated function for each integration test. Simply as that! Each file, will be compiled and ran as a different integration test, no ``mod`` or other declarations and not even ``lib.rs``, ``mod.rs`` or ``main.rs`` files.

#### Common functionalities
But how do we define common test functionalities, which multiple integration tests may use? We simply create a ``common`` folder inside our ``test`` folder. We then proceed by adding a ``mod.rs`` file, where functionalities will be exported. This folder, follows the usual Rust module declaration format. We then import these functionalities in each integration test using the ``mod common;``  declaration.

Rust will automatically compile the ``common`` folder in a different way than tests and won't run it or its functions as a test.