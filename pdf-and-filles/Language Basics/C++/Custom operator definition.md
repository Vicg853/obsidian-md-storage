Consider the case where we want add two custom data structures (e.g.: two classes). C++ allows us to define custom operator behaviour for such data structures, that are then swapped at compilation time.

To define custom operator behaviour, we define a function called ``operator`` followed by the operator token (e.g.:``+``, ``==``).

For example: 
```cpp
class Test {
	int a;
	int operator+(Test&)
}

int Test::operator+(Test& other) {
	rerturn this->a + other.a;
}
```
Now we are able to perform operations with the ``+`` operator between two variables of ``Test`` type.