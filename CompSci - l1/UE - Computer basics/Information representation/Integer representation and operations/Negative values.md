How is it possible to represent the "+" and "-" values in a computer. Well, we know that we have only two symbols, therefore we can simply represent them with ``0`` -> ``+`` and ``1`` -> ``-``. 

Its like if we were asking the question: is the number negative: 1 = yes and 0 = no.
Then we put this as the first bit on binary representation from the left to right. 

But there is actually some catches with this:

#### Bytes again
The first one, already [[CompSci - l1/UE - Computer basics/Information representation/Integer representation and operations/Intro#Bytes|stated before]], are the representation's format rule. 

This rule help us to find out where to place our negative sign: at the start (from left to right).

With this, there is an only constraint that appears, we will lose some represented values, as now, we are using one of the bytes as a sign.

We now discovered the called: "one's complement"

#### The actual representation
The biggest problem, that the "one's complement" still features is that: our calculations will give wrong results. 

Lets say we have 4bits, with the first one being the negative sign. In "1's complement" we would have ``1 = 0001`` and ``-1 = 1001``. If we add ``1 + (-1)`` we would end up with ``1010`` which is equals to ``-2``... Which isn't right. Because, it should be ``0``.

A second problem is we have an additional value, that that 1's complement solves by creating a second 0, therefore we have ``0`` and ``-0``, which could cause some additional useless complexity.

## Two's complement
We therefore came with "2's complement", it solves both issues stated above. 

In this version, instead of having simply values with a different 1 or 0 at the start we actually change its whole representation too, by simply following an equation: 

![[Screenshot 2022-11-18 170145.jpg]]
Summing all up: we can find any integer's negative representation, by simply switching all bit's and then adding 1 it them.

This can be mathematically translated to $(2^n-1)-n+1$.

And the double 0 problem: instead of adding an additional ``-0``, we represent an additional integer: ``-8``, which won't modify calculations. Now, any addition will go right.

This will result in the following representation table: 
![[Screenshot 2022-11-18 170145 1.jpg]]