We saw how we [[CompSci - l1/UE - Computer basics/Information representation/Integer representation and operations/Intro | represent integers ]] with binary values, but better than interpreting/representing integers, is calculating them.

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
