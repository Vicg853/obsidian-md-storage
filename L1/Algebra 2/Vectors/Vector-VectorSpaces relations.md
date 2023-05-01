A sub-space can be geometrically explained, as a space's inner space, in other words, we have a coordinates set, belonging to $B$ and at the same time to $A$, which contains those coordinates among others. Therefore we have $B$ as a sub-space of $A$.

When we are precisely talking about vectors, as we're doing on this whole page, the concept is pretty similar, we just change the fact, that instead of coordinates/points, we are using vectors.

#### Intersection
An easy way (but not always possible from ground-up) of determining that a space is someone's sub-space, is by concluding that it is the intersection of two or more of a space's sub-spaces.

For example: consider the following $\Bbb R^3$'s sub-spaces, $(a_1, b_1, c_1), (a_2, b_2, c_2)$. 
$$I = \left \{ (x,y,z) \in \Bbb R^3 : \left \{ \begin{matrix} (xa_1, yb_1, zc_1) \\ (xa_2, yb_2, zc_2)\end{matrix}\right . \right \}$$

As we can see, based on the sub-space's algebraic properties, we can say

#### Belonging properties
Let's consider $F$, a vector space and $K$ another vector space. $F$ is considered $K$'s sub-vector, if it meets the following expectations:
- first $K$'s null vector, must be a part of F: $0 \in F$;
- it respects $K$'s vector-to-vector operations. In other words, any sum of two of $K$'s vectors, must result in a vector that exists in $F$
- its respects $K$'s scalar-to-vector operations. In other words, any product between a scalar and one of $K$'s vector, must result in a vector that exists in $F$.

There is only a small clarification, about something that must be understood in the above statements: actually, commonly, the statements are made, by first assuming that $F \subset K$ and therefore we usually take the vectors from $F$ to test the expected properties, instead of the opposite. 
The way of thinking used above, was used without previously making this assumption, should come to the same conclusion in the end.

It can concisely bring things together and use two simple properties, allowing us to check if $F$ is one of $K$'s sub-vector space: 
- $F \not = \emptyset$ (as it must at least contain the null vector)
- and considering two vectors $x, y \in F$ and $\lambda, \mu \in \Bbb R$, the vector $\lambda x + \mu y\ \in F$