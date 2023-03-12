We may want sometimes, to have access of a class' private members, inside a non member-function. 

C++ allows us to do this, by defining a "friendship" relationship in its declaration. We therefore  define the function, by first using the keyword ``Friend`` followed by the corresponding function's header.

For example:
```cpp
class Test {
	//...
	
	Friend ostream& operator<<(ostream&, Test&)
}
```
Now we are able to declare this corresponding function and have access of "Test"'s class private fields