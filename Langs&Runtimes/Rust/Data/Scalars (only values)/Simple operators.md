Rust supports simple but always expected mathematical operations: addition, subtraction, multiplication, division (which is rounded up to the nearest integer), and remainder. 

```rust
fn main() {
    // addition
    let sum = 5 + 10;

    // subtraction
    let difference = 95.5 - 4.3;

    // multiplication
    let product = 4 * 30;

    // division
    let quotient = 56.7 / 32.2;
    let floored = 2 / 3; // Results in 0

    // remainder
    let remainder = 43 % 5;
}
```

## Other
The full list of operators, with more "complex" operators, can be found under https://doc.rust-lang.org/stable/book/appendix-02-operators.html#operators.