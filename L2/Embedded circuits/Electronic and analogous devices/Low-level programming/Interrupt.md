Interrupt consists of a procedure having a slight priority over the core program, therefore, when requested, the core program is paused, for the interrupt program to be executed. 

Functions with such properties are called: _Interrupt service routine_ functions and their triggers (that can be of both physical or virtual form) are called _interrupt request_. ISRs are asynchronous processes, as we are not sure when the core program could be "stopped".

> [!TIP]
> It is important not to use blocking procedures inside an ISR, as they may cause code blocking

#### ATmega328p interrupt vector table
Here are the default interrupt signals used by an ATmega328p processor (usually present in Arduino UNO devices). 
It is worth knowing that the higher a vector n, the less priority it holds.
![[interrupts.png]]

#### Arduino C/C++ interrupts
Coding interrupts in Arduino using C/C++ is pretty straightforward. To set it up, you're only required to call a function accepting the interrupt vector, the ISR's function pointer and the mode (defining if it should be called on a HIGH/LOW state, or in a rising/falling edge, etc.).

The function used under theses circumstances is the ``attachInterrupt(``[pin]``, ``[ISR]``, ``[mode]);`` function.
