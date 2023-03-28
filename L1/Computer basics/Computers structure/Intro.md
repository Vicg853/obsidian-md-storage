What we call a "computer" is strongly general and doesn't consider a variety of sub-labels we give them: sever, PC, mobile phone, tablet,...; Which usually reference a certain characteristics of tasks we devote/assign them to. 

A computer actually in general, is a machine, which can perform complex calculations and should in theory, perform any type of calculation. Therefore, when producing computers, we should follow a common set of things, so those are able to perform any calculation, which isn't known at the moment of its creation.

Hence the Von Neumann model: the current mostly accepted based architecture, used across devices. This model is composed of four main elements:
- The main Arithmetic and Logic unit (or ALU for short), tasked of making all the required elementary calculations (mathematical operations ($+, -, \times, \div$), boolean logic, floating point arithmetic, ...) (note that its capacities can also vary. Each ALU usually has its own set of capabilities)
- The control unit (usually called "chipset" on bigger computers (PCs, servers))
- The memory(ies) which stores a calculation's instructions and current runtime progress. The two most common type of memory seen in most devices are: ROM (Hard Drives, SSDs, ...) which stores long term memory (programs) and RAM which stores runtime data (variables, file caches, ...). There also other common storage devices, that are mostly platform specific: CPU L1/L2/L3 caches, ...
- An output and an input device, which controls and interfaces communications with other devices and with programs: ports, stdout, stdin, ethernet, USB and other such as these. There is almost an infinity of them and they vary A LOT between computers.

Putting the core elements aside we are also gonna turn our eyes to some of the smaller parts that compose a computer and even ALUs:
- [[Multiplexers & De-multiplexers]]
- [[Encoders & Decoders & Transcoders]]
- [[Busses]]

##### Operations
Well, but are does all this structure serves for? 

In a nutshell, all this results in a single outcome: boolean operations. Simple ones and zeros and boolean arithmetic, that turn into numbers, characters, electrical/light signals and many more.

These operations, are ran on complex circuits following boolean logic, which are  abstracted into functions and variables [[L1/Computer basics/Information representation/Intro|as seen here]].