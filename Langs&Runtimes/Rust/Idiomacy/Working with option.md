By default, the Option enum, implements the Iterator trait, which can be extremely helpful in many cases.

Here are some of the examples where the option enum can be applied with the iter trait.

#### Inserting option
When inserting an optional value into an iterable element (e.g.: a vector), instead of checking it with an ``if`` statement, followed by a ``.push()`` call, we may simply use the ``.extend()`` method. 

It will check for the option's ``Some`` variant to insert the underlying data, while it would just ignore for a ``None`` variant.

```rust
let c = Some("C");
let my_none = None;

let my_vec = vec!["A", "B"];

my_vec.extend(c); //c will be pushed into my_vec
my_vec.extend(my_none); //while my_none will not be pushed into my_vec
```

#### Chainning
We may chain iterators into another, this can also be applied to ``Option`` wrapped elements.

(consider the previous code)
```rust
for el in my_vec.iter().chain(c.iter()) { //We are appending c into my_vec and iterating over the produced iterator
	println!("El: {:?}", el);
}
```

#### flatten method
When working with a vector of ``Option``ed elements, we may want to filter out None elements and return some's underlying values. For that, we have the ``.flatten()`` method.

```rust
let optionals_vec = vec![Some("A"), None, Some("C")];

let optionals_vec = optional_vec.into_iter().flatten();
//Now optionals_vec is ["A", "C"]
```

#### The ``.Ok()`` method
Both the ``Option`` and ``Result`` enums, are widely used... Sometimes, we may want to even switch from one to another. For that, we have the ``.ok()`` method.

```rust
fn a() -> Result<String, Err> { /*...*/ }

let b = a().ok(); //Now we have an ok variant
```
