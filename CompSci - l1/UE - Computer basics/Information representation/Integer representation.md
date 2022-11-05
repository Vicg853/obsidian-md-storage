We can't simply represent integers with an only ``0`` or ``1``, we need a combination of them. They will allow us to do it.

The thing is, in mathematics, we have numerous categories of numbers and an infinity of them. Creating combinations infinite combinations, can become hard and wouldn't be scalable.
The idea is defining a set of limited integers, that can serve as base to represent any other integer and then, create groups of Boolean (or Binary, from now this will be the term used, as it fits better our environment) combinations. 

We are then be able to represent an infinity of numbers and representations, as these, are easy to manage. 
This technique is therefore used on all levels: at a basic one with integers and letters, then we could go deeper with ASCII, UTF and etc. They all use the idea of creating a basic set of elements, that can be used to creating many others (think of painting's color palettes: yellow, red and blue).

### Representation
To represent integers, we only need to know how to represent from 0 to 9, as all other integers, are a represented as a combination of two or more of these integers together: ``99`` is ``9`` and ``9`` side by side and etc.

We therefore define a base, that corresponds to the number of integers necessary in a packet binary elements. For example a base of 10, will contain 10 ``0``s and ``1``s used for representation. We then assign each combination to a value that we will to represent. 

For example: 
![[Pasted image 20221105011816.png]]

### Mathematical theory
We may use a mathematical representation that allows us to tear apart or find a representation. 
$$N = \sum_{i=0}^{k-1} r_i\ \cdot \ b^i$$

$N$ is usually noted: $(N)_b$

|Symbol|Meanning|
|--|--|
|N| represented integer|
|k| representation's length|
|$r_i$| the $i$th element |
|b| representation base |

For example this translates to (with $N = 563, k = 3, b = 10$): $563 = 10^2\ \cdot \ 5\ +\ 10^1\ \cdot \ 6\ +\ 10^0\ \cdot \ 3 = 10^2\ \cdot \ 5\ +\ 10\ \cdot \ 6\ +\ 3$



