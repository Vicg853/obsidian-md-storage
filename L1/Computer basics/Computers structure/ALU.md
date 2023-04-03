The Arithmetic and Logic Unit, or ALU for short, is considered a processor's core. It is expected to perform all logical and arithmetic operations like: multiplication, equality comparisons, ... (more in a minute).

It can also sometimes, be introduced under a different name and increased capabilities: floating point unit (or FPU, capable of performing arithmetic and logic operations on floating point numbers), vectorial processing units (optimized to mainly perform array and vector operations)...

Nevertheless, even with such differences they still follow a pretty standard format: 
![[Pasted image 20230403165701.png]]

Each of the components' description:
- The two operand sections are assigned to receive data on top of which operations will be performed. It also partially defines a so called ALU power, by using the data's input bit count, e.g.: an 8bit ALU, 32bit ALU, ...;
  Sometimes, it may be necessary to expand its power/capacity. In this case modifications can be performed, which may as counterpart reduce its calculation options and limit some of its vocabulary on another side (a.k.a. un-consider the negative bit, which could increase input values, but would remove negative values)
- Command input, defined on a group of single activated bits, that define which operation must be performed on the entered bits. Among almost limitless operations, the most known would be:
	- arithmetic: addition, subtraction, multiplication, division, modulo, ...;
	- logic: "or" and "and" comparisons; "inferior", "superior" and "equal"; ...;
	- bit operations: translation, bit-wise "or" and "and" operations (OR, AND, XOR, XAND, ...), ...;
- The result, containing, well..., an operation's result.
  This element, can also limit the ALU's called power, as some operations may require more bits than its output can handle (such as multiplication, which could sometimes double the required output's bit count, compared to the operands' sizes)
- [[Flags - Status|State (or flag)]] outputs, which behave similarly to the operations input: a single bit for each one, although that for states, many can be true in parallel. 
  They are used to represent and broadcast information about a calculations' status.

