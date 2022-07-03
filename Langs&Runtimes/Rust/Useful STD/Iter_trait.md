The included iterator trait can be used to iterate over any data type to which it is implemented, without using methods instead of loop keywords as ``for``, ``loop`` and ``while``. 

It can help you prevent big boilerplates and make code more concise/readable. 

To full and correct trait name used to implement data is: ``Iterator``. 

Rust's built-in data types already implement this trait. 

## Requirements
The only requirement brought by the iter trait, is defining the ``.next()`` method. 

## "Sartup"
To be able to iterate over elements, you must first call the ``.iter()`` method.

Although, there are two variants to this method: 
- ``.into_iter()`` takes ownership of the iterrable values
- ``.iter_mut()`` borrows elements as mutable instead of immutable as in the default ``.iter()`` method
## Main useful to know methods
- ``.next()`` goes to the next iterator element at each call and returns ``None`` after the last element
- ``.map()``: receives a closure as parameter and runs it for each iterrable element 
- ``.sum()`` sums all inerrable elements
- ``.filter()`` receives a closure with a bool result and excludes or includes an element to the final output based on it. 
- ``.collect()`` transforms raw iterrable into natural collection data type

## More
- [https://doc.rust-lang.org/std/iter/trait.Iterator.html](https://doc.rust-lang.org/std/iter/trait.Iterator.html)