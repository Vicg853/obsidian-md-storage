We may usually need to control, how we run our test, which ones we run and which ones we do not. 

And we have methods to do it both on the CLI with the ``cargo test`` and code that will specify our desired actions.

## Ignoring test
#### Code
Sometimes, we may want to always exclude specific test, until second notice. We have the ``#[ignore]`` macro attribute for that. You just need to assign a test function with it (always after defining it as a test function).

```rust
#[test]
#[ignore]
fn expensive_test() {
    // code that takes an hour to run
}
```

We use the ``--ignore`` flag to run ignore attributed tests. It should be declared after the a ``--``  and ``--include-ignored`` to run both ignored and non-ignore attributed tests.

#### Filtering
You may filter which tests are run by name. After the ``test`` subcommand, the first arg specifies the pattern of test that should be ran. Rust will seek for all test names that contain the specified argument string. 

We may use it to run only tests by passing the entirety of the test's name as argument, therefore only matching this test's name.

```bash
cargo test test_addition 
cargo test test_
```

## Output
Output is captured during tests, but they are only shown, when a test fails. The same applies to tests which we use ``println!()`` for debugging for example. Successful test, will only print an ok message after the test's name.

If you want all tests to have their output printed, even successful one's, you may pass the ``--show-output`` flag after the ``--``. 

## Threads
As declared in the intro, tests are multithreaded tests. You may want to narrow threads sometimes. There is a flag for it: the ``--test-threads`` flag, which accepts an integer. It is passed after ``--`` to ``cargo test``.