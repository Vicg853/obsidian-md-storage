Representing decimal numbers, can be tricky and it mostly comes to: the range of integers we may need to represent and the space that this consumes.

For that many solutions have been explored for years, with different architectures and mathematical expressions.

Here are some tries:
#### 2 successful integers
We could just split an integer in half and consider it two different integers, one half comes before the comma and the others after it (from left to right). 

The problems with this are: 
- If we change the byte size in a number, how should additional zeroes be handled in de right-hand side: $111.101 = 7.5 \ne 0111.1010 = 7.10 = 7.1$
- And if we follow this method, using two's complement, how do represent $-0.5$ for example, while $-0$ does not exist in two's complement

#### Fractions
We could use fractions. But, they present the same problem with comparison presented by [[#2 successful integers| 2 successful integers representation]].

#### Powers
It could be a solution and will actually serve us later, but, alone it can't do much. We now have a big precision issue, that can be really solved and we still have the negative 0 value, that can't be represented.

### Floating point
We finally come to the solution: scientific notation. It allows us to create huge values, with little storage and with a reasonable precision (as it is usually even used for scientific purposes). Which will fit most cases. 

More about it [[Floating points|here]] and its also important to know that the IEEE standardized [[IEEE 754|floating point numbers]] in the 754 convention.