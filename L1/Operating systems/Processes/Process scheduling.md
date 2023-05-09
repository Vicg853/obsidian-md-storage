A CPU is actually single threaded (we're not talking about multi-core processors, but actually a single thread), so, the OS actually creates the illusion of multiple programs running at the same time: it switches between all of them, very quickly.

#### Context (state)
Without memory, this wouldn't (or actually anything else) be actually possible. For this, the CPU saves data used by a program, in it's previous instruction. 

Remember that, instruction are simple memory changes and operations, in assembly, therefore, it is "easy" to a certain point, for an OS to stop and save a single (or group of them) into memory and the address of the last's executed instruction.

This is key for any process scheduling, as without this, we wouldn't be able to switch between tasks.

####  