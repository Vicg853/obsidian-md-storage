## Intro
Virtually, the RAM (or Random Access Memory) is split into three main sections:
- [[#Static memory]]
- [[#The Stack]]
- [[#The Heap]]

### Static memory
It consists of the "lowest" memory level: it has a static size and stores variables defined in a binary and is automatically cleaned when the program lifetime ends (a.k.a. termination).

### The Stack
This section stores function arguments, function local variables and just as static memory, its size is known at compile time, fixed and cleanup is automatic. The only diference is that memory is cleaned when the corresponding function's lifetime ends and not at program termination.

### The Heap
The delicate one: here are stored global variables, variables accessed outside a function's scope, multithread values and variables with unknown or larger sizes. 
The thing about the Heap section is that its cleanup and declaration is fully manual. With that, issues probability increase, as we must consider human error and limits. 

To fix that we have three most known solutions: [[Management - RAII]], [[Management - Garbage collector]] and [[Management - Ownership]].