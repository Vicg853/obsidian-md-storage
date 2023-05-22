If memory didn't exists, nothing we do would be possible: we depend on remembering past events. On a computer, this isn't different, remembering things, either on a short or long term, is essential. 

Hence storage devices and, on small scale, circuits.

But memory circuits, couldn't be crafted with usual combinational circuits, they require [[Temporal Circuits|non-combinational]] (or temporal) circuits.

#### Composition
At their core, memory modules can differ on their composition. The most basic one and probably the founding one uses the [[Flip-flops|flip-flop circuit's]] concept. 

Moreover their composition can vary:
- simple magnets on current Hard Drives
- current SSDs are mostly composed by NAND technology, based  of silica and a group of transistors that allow data to be stored without any energy source

##### Simplest
Going back to the most basic memory type, it usually uses a [[Flip-flops#D| D type Flip-Flop]], which only registers a value on when receiving a specific signal. 

We can use this flip-flop and adapt, by creating a R/W signal input and a value input. In case of read, we also activate a [[High impendance|HI (High Impedance)]] module hooked to the output preventing it from being transmitted and therefore, join input and output in a single cable for simplicity.

We now have a very standard and simple memory storage circuit, with read and write capabilities with two simple inputs.

(the image bellow also  considers a HI module for the input, as its input and output are separated and not joined as a single element)
![[Pasted image 20230521205010.png]] 
