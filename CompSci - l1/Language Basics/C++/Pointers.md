A pointer is defined using the ``*`` operator and they me declared with any existant data type.

```cpp
int main() {
	int * p = new T[100];
}
```

You may declare empty pointers, that will in the future point to something. 

#### Structures 
When working with structures and pointers, there is a special syntax, that allows us to edit data present inside the respective struct: ``the -> arrow``.

```cpp
struct A {
	int x;
}

int main() {
	int * p;

	p = new A;
	p->x = 0;
	std::cout<<"x: "<<p->x;

	return (0);
}
```

#### Accessing values
To actually access the value to the pointed value, we must again use the ``*`` operator.

```cpp

```
