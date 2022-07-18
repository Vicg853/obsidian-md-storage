Although Rust is mostly safe as fuck, we can still stumble upon memory issues in some cases.

It can happen for example, when creating cycled references using the Rc smart pointer (about the [RC smart pointer](../Data/Smart_pointers/Rc_(aka_reference_counting))). By doing this, we could possibly a memory leak when dropping one of the values. 
It could be even worst if we for example created a cons list, that prints child elements through a method, which could result in a stack overflow, as the methods could be called infinitely when creating cycled references. More about both cases here (https://youtu.be/pIVZRDFAUyc).

So you must proceed with caution, when Rc and etc are required, and always pay create tests, do code reviews, memory test/profiling, among others to prevent issues. 

Another solution for the Rc problem, is using a [weak reference count](../Data/Smart_pointers/Weak) pointer. 