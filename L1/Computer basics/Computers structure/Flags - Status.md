Flags (or statuses), are bits used on a circuit, to represent and broadcast information about a calculation performed by a circuit. It is very importantly and commonly used in [[ALU|ALUs]].

A really narrow use case can be in an addition circuit, when outputting a carry bit (which actually consists of a status bit), that can be passed onto the next addition circuit and so on so the final result can be found. Example: 
![[Pasted image 20230403172808.png]]
![[Pasted image 20230403172826.png]]
![[Pasted image 20230403172840.png]]


#### ALUs
It is common for [[ALU|ALUs]] to contain multiple status bits. The most common among many can be: 
- The "Zero Flag", which states if an operations result is equal to 0;
- The "Overflow Flag", stating if an overflow occured during calculations;
- The "Carry Flag", stating if the operation outputed a carry bit, allowing for a calculation must be re-performed with the ALU in a increased capacity mode, etc...
- The "Sign Bit": stating if a result is negative or not
- The "Parity bit": stating if a result consists or not of a pair integer
- etc...

Note that, inside the ALU, these flags, are mere analysis of the core operation's result and can be found by making an analysis of the operators and results