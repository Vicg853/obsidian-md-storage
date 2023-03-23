An operating system plays the role of abstracting the hardware, from the program. It makes operations easier, allows us to schedule multiple programs to be run beside each other and allows the program to be partially independent from the hardware. 

Long story short, the operating system looks more or less like: 
![[Pasted image 20230323150238.png]]

Apart from the things mentioned above, the operating system also manages:
- manages files and directories (physically and its appearance)
- Memory management (as already mentioned): it ensures that programs only use their provided memory space and that each program can have its memory space
- Program management (as mentioned)
- I/O management: keyboards, sound peripherals, general peripherals and also inner hardware such as graphic cards, memory on itself, ...
- [[L1/Operating systems/Command line/Intro|Command line]] management
- U.I. management

#### Need
The first computers, such as the ENIAC, didn't have an operating system. They were used for simple computing: calculating projectile trajectories, cryptography, etc...

With the absence of feature such as: scheduling operations, infinite loops, command automatic chaining and memory management, made programming in these computers not possible. They were hard-coded, which required a developer to do double the work, the program to be redone from ground-up when it errors and limited us to a single process the be ran at a time.

Also, as we were closer to the hardware, a program had to be moulded for each and every system it runs on.



