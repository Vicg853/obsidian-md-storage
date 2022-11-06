We use a combination of bits to represent numbers in a computer. Each exact combination set, represents a single integer and this certain combination is defined by a convention, e.g.: 

|Binary|Decimal|
|--|--|
|0000|0|
|0001|1|
|0010|2|
|0011|3|
|...|...|

This convention follows the [[Base representation theory#Mathematical theory| base representation mathematical theory]]. Therefore the decimal representation of ``0011`` is justified by: 
$$0011 \iff 0 \cdot 2^3 + 0 \cdot 2^2 + 1 \cdot 2^1 + 1 \cdot 2^0 = 3$$ 

### Negative integers
How is it possible to represent the "+" and "-" values in a computer. Well, we know that we have only two symbols, therefore we can simply represent them with ``0`` -> ``+`` and ``1`` -> ``-``. 

Its like if we were asking the question: is the number negative: 1 = yes and 0 = no.
Then we put this as the first bit on binary representation from the left to right. 

But there is actually a catch with this.