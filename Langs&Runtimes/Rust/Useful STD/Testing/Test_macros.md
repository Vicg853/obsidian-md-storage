The standard library, provides many tools, to extend and improve Rust's testing experience and versatility. Here are some of them, or at least the most important ones:

## Panicking
Sometimes, panics are useful and handle something which requires panics and we may want to check if our program actually panics on those cases.

The std library provides the ``#[should_panic]`` macro, which assures that a thread will panic. If it panics, then, this test is successful. 

```rust
#[test]
#[should_panic]
fn this_panic() {
	panic!("AAAA!!!");
}
```

But panic test can be inaccurate sometimes: what if our functionality panics... but not at the right place. The ``expected = ...`` arguent fixes this issue: it should be passed to the ``#[should_panic]`` macro as an parameter and  assigned to a string.

Rust will then check if the panic's result, _contains_ the expected string.

```rust
#[test]
#[should_panic(expected = "Expected ")]
fn check_panic() {
	if true {
		panic!("Expected panic!");
	} else {
		panic!("Wrong panic!");
	}
}
```

## Results
Although panic is useful, in most production cases, we may want to handle things gracefully. 

Hopefully we may uses functions that return a ``Result`` type and use the question mark operator to handle it! And empty ``Ok`` result, is interpreted as a successful test, and a string wrapped by an ``Err`` variant is considered a failed test.

```rust
#[test]
fn it_works() -> Result<(), String> {
   if 2 + 2 == 4 {
	   Ok(())
   } else {
		Err(String::from("two plus two does not equal four"))
	}
}
```

When trying to achieve failure (expecting that a failure occurs), neither the question mark operator, nor the ``#[should_panic]`` macro, should be used. Instead, use the ``assert!()`` macro, passing the respective tested result, using the ``.is_err()`` method. As an ``Err`` variant, means a failed test.

```rust
assert!(my_result.is_err());
```

## Assertions
There are three main assertion test macros. They are function like macros and should be used inside a test function's scope.

#### assert
The ``assert!()`` macro, simply verifies a statement or expression is truthfulness's.  

```rust
#[test]
fn my_test() {
	assert!(true);
}
```

#### assert_eq
The ``assert_eq!()`` macro will assure two statements or expressions equality. 

This macro uses the ``==`` operator under the hood, which requires that a type must implement both the ``ParttialEq`` and ``Debug`` trait to be compared. 

```rust
#[test]
fn my_test() {
	assert_eq!(2, 2);
}
```

#### assert_ne
The ``assert_ne!()`` macro will assure two statements or expressions inconsistency. 

This macro uses the ``!=`` operator under the hood, which requires that a type must implement both the ``ParttialEq`` and ``Debug`` trait to be compared. 

```rust
#[test]
fn my_test() {
	assert_ne!(3, 2);
}
```

#### Custom error messages
All three assertion macros mentioned above, accept an optional parameter, followed then by other variable number of parameters.

All optional parameters will be forwarded to a ``format!()`` macro, which will format the output a formatted error message. 

The first optional parameter, corresponds to the string which should be formatted by the ``format!()`` macro, the following ones are the arguments used within the string.

```rust
#[test]
fn greeting_contains_name() {
	let result = greeting("Carol");
	assert!(
		1 + 1,
		"Weird... 1 is not equal to 1... This should be impossible 🤨"
	);
}
```