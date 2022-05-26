"Resource acquisition is initialization (RAII) is a programming idiom" ([Wikipedia](https://en.wikip edia.org/wiki/Resource_acquisition_is_initialization)) that is mostly associated with the C++ programing language. 

In computer science, random access memory is a short resource and its management can be hard and error prone in a field full of feasible memory leaks, security breaches, stack-overflows, etc. 

RAII, is one of the programming idioms that tries it best solving this issue and is considered an excellent practice. 

It consists of basically creating data pointers to new classes, each class defining a constructor that will assign the value to the heap and a destructor that will later automatically detach it.

### Advantages
- Full control over variables
- Efficient
- Error free

### Cons
- Somewhat tedious