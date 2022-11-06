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

And how are negative values represented? Well, this is another subject

### Binary addition
Binary addition can be done in a similar way as decimal addition, the only difference being that the ``+`` operator actually corresponds to the ``XOR`` Boolean operator. Therefore 

|Operation|Result|
|--|--|
|0 + 0|0|
|0 + 1|1|
|1 + 0|1|
|1 + 1|0 (and 1 as overflow)|

> [!NOTE]
> Why is ``1+1 = 0`` plus ``1`` as rest. Well, think that in decimal, 1 + 1 = 2... but 2 does not exist in base 2. 
> Therefore we need another combination to represent 2: ``10``
> Therefore each time we ``overflow`` in an addition, we actually add an ``1`` to the sequence.

_More complex example_: well, adding two simply bits is fun and everything, but we need to do more than this. Let's add 5 and 4. Therefore: ``101 + 100``.
Just as we learn as kids, we can do a simple addition operation (remember, that we push rests to the next column):
$$\begin{align}
_{+ 1}\ \ \ \ \ \ \ \ \ \ \ \ \\
\ \ \ \ 1\ \ 0\ \ 1 \\
+ \ \ \ \ 1\ \ 0\ \ 0
\over
\ \ \ 1\ \ 0\ \ 0\ \ 1
\end{align}$$

### Binary subtraction
