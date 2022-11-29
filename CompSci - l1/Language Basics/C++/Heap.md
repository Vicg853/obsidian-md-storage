To do heap annotations in c++, we must do it manually. Any other allocation is usually done on the stack. 

Therefore, we have two keywords to work with it: 
- ``new`` which allocates memory in the heap
- ``delete`` which frees the respective allocated memory

Note that memory may not always be available, or another error may occur while asking for new memory allocations. 

