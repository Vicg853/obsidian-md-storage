An operating system plays the role of abstracting the hardware, from the program. It makes operations easier, allows us to schedule multiple programs to be run beside each other and allows the program to be partially independent from the hardware. 

Long story short, the operating system looks more or less like: 
![[Pasted image 20230323150238.png]]

Apart from the things mentioned above, the operating system also manages:
- manages files and directories (physically and its appearance);
- Memory management (as already mentioned): it ensures that programs only use their provided memory space and that each program can have its memory space;
- Program management (as mentioned);
- I/O management: keyboards, sound peripherals, general peripherals and also inner hardware such as graphic cards, memory on itself, ...;
- [[L1/Operating systems/Command line/Intro|Command line]] management;
- program and general hardware inter-communication;

In a nutshell, an OS works as an interpreter (the person, not the program) between programs and the computer's physical resources (hard drives, USBs, I/O, ...), as well as assures users/programs isolation/runtime and resource control/access.

#### Reason
The first computers, such as the ENIAC, didn't have an operating system. They were used for simple computing: calculating projectile trajectories, cryptography, etc...

With the absence of feature such as: scheduling operations, infinite loops, command automatic chaining and memory management, made programming in these computers not possible. 
Things were hard-coded, which required a developer to do double the work and programs to be re-coded from ground-up when it errors and limited us to a single process the be ran at a time.

Furthermore, even with second generations, where multiple program instructions could be chained up, there was still an authorization and concurrency problem.

Nevertheless, even with each newer generations a same set of problem kept showing its face again and again:
- missing per user customization
- missing per program isolation (preventing global crashes and unexpected memory modification)
- hardware diversification
- I/O compatibility diversification

#### Working with an OS
There are many interfaces provided by and other specificities inside an OS allowing everything to work properly to work with it. Here are some of them:
- the [[Terminal & shell|terminal]] providing a standard and powerful communication between both parties (user - computer)
- disk [[File systems|file systems]] and [[Disk repartition|disk organization]] allowing everything to be neatly stored in storage devices
- 





