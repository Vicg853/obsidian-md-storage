Circuits communicate between them, sometimes, a single one with multiple ones, or across different [[Busses|bus types]]. To fill this need, multiplexers and de-multiplexers where developed.

These are circuits, that transform a single input, into several ones, or vise-versa. 

They are composed of three main components: 
- input(s)
- exit(s)
- address inputs
- and a chip-select bit, allowing it to be turned on or off

On each case, the input and exit count can change: 
- on multiplexers, we have a single input, which is converted into several outputs
- on de-multiplexers, we have several inputs being bottled-down to a single output

As we are talking about circuits, therefore the hardware level, there two simple mathematical statements that can help us find the number of inputs/outputs for a respective mux/de-mux:
- for a multiplexer, a serial bus handling $n$ input bits will ouput $2^n$ bits
- for a de-multiplexer, a parallel serial output handling $n$ bits, will require $2^n$ input bits

#### Bus usage example
One of this circuitry's most common use cases is the conversion between serial and parallel bus types.

When converting for example a serial bus into a parallel, we are using a multiplexer. The serial bus is the input and the parallel the output. Each time a new cycle ends, the address is incremented, so that bits are forwarded to its respective parallel "cable". 
Therefore the signal which was before serial, is now parallel.