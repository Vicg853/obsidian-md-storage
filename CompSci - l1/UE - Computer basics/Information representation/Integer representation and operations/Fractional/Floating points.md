### Scientific notation
The floating point numbers come from the idea of scientific number notation, such as the speed of light: $3.00 \cdot 10^8\ m/s$. 
It allows us to have precise numbers, while requiring little space.

Scientific notation is always represented with the following mathematical expression: 
$$\begin{align}
M \cdot b^e
\\ M = \mathsf{the\ mantissa}
\\ b = \mathsf{base}
\\ e = \mathsf{expoent}
\end{align}$$ 

The mantissa's size will define the result's precision. 

### Floating points
In computer science and floating point numbers, we apply this this method in a particular way:  we store a byte and split it in two parts: one which stores the exponent and another the mantissa. 

Both the mantissa and the exponent are represented in two's complement by themselves. Which states that they can also be negative by themselves.

### IEEE 754
But, it can be quite confusing on how to correctly define how much each respective part's size, position and etc.

For that the IEEE defined standard for two floating numbers representations, which can be discovered [[IEEE 754|here]].

### Conversion 
#### To base 10
To convert a binary floating number into base 10, we consider that the dot is positioned just after the first bit, e.g.: ``1.101``. We convert the exponent into base 10 and move the point from exponent times to the right, if its a positive exponent or the left, if it is a negative one. 

Based on the position of the point, we convert the binary values using the basic base conversion rules, with the only characteristic being: the numbers to the right of the point are negative powers of two and to the left, they are positive.

#### From base 10
To convert from base ten we convert the integer into binary, using two's complement and base conversion rules. Then we must move the point, into two possible ways:
- if it is a negative we need to move the point at the right of the left most 1 that is directly followed by a 0, therefore ``1.0`` 
- if it is a positive one, to the right of the left most 0 which is followed by a one on its right, therefore: ``0.1``
Our exponent, is defined by how many times we should move the point for it to be back to its original position. Note that, it should be negative if it moves to the left and positive if it moves to the right. 

The original comma's position, is always a barrier between integers and fractional numbers. 

Note that when converting, e.g.: ``-13 + 0.5 = -12.5``, therefore, pay attention when finding the integer part of a number in a binary conversion table.

### Normalization
There are technically many ways to represent floating point numbers, even in normal scientific notation. The idea of normalization, is to always position the dot, to the right of the most relevant number, which will:
- maximize precision
- omit ambiguity 
- and facilitate arithmetic operations, as computers don't need to convert to similar formatted numbers

Following the above techniques, should result in normalized results.

#### Negative normalization

#### Positive normalization