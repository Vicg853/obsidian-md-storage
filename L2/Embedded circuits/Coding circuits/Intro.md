## VHDL
Among many of the tools used to create hardware circuits, the VHDL is one of the most standard ones. 

It consists of a procedural language, with the specification of transforming written instructions in physical circuit nodes and combinations, making its resulting logic one of the fastest. 
It has a pretty strong C like structure.

Most of its syntax consists of procedural description language, that is: it describes inputs and outputs, gates for a certain "[[#Entity|entity]]", which can be used and mapped into properly adapted hardware interfaces. 

One of its key characteristics, different from C logic, is that, usually, instructions defined inside an entity, are executed in parallel, instead of top-down steps.

As for other specific syntax and characteristics characteristics:
- it is strongly typed
- it lacks case sensitivity
- comments are placed after double lines "``--``"
- it contains [[#Processes | processes]] (not the same as a virtual or OS process)



#### Entity
An entity consists of a definition block, with hidden details from the outside user's point of view (aside from input, output and Input/output ports).

In its insides, as an user having access to its definition, you can define and modify what is called its "architecture".

#### Processes
Processes in VHDL could be more or less compared to asynchronous code in higher level coding (not to be confused with hardware level asynchrony, where entities don't not follow clock set rythm). 

On an essential level, it does follow clocks orders, but is usually stuck in a "loop" state, awaiting for one or more dependency(ies) change (which is notified by circuitry by an output value).

We could otherwise, also compare them to "signals" in high level code.
