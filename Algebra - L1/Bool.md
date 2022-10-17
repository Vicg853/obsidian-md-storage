Boolean algebra, bases itself on True and False statements. It can be used in multiple places, but mostly to judge if statements are valid or not, where valid means "True" and invalid "False".

Mathematically, we often use $P$ as notation for a variable that stores a boolean statement.

$$P =  1+1 \implies P = False$$

#### Negation
We can also negate boolean statements, we often use $\lnot$ symbol as a notation for it, e.g.: $\lnot P$. 

The negation of a boolean value, is equal to its opposite: if $P_1 = True$ and $P_2 = False$ then $\not P_1 = False$ and $\not P_2 = True$.

#### Conjunction
A boolean conjunction is when we assert that two boolean values are valid. We could more easily illustrate this with "P and Q" or mathematically $P \land Q$.
This means that $G = P \land Q$ is only True if both $P$ and $Q$ are true.

#### Disjonction
Similarly to conjunctions we have disjonctions, the difference is that disjonctions require that at least only one of the assertions are valid. The illustration for it is "P or Q" or mathematically $P \lor Q$

#### Implication
An implication can be compared to computer science's xor gate. It implies that either a statement P is invalid or a statement Q is valid. It is mathematically stated the following way $P \implies Q$. We could make this more understandable the following way: $Q \lor \lnot P$

#### Equivalence
Equivalence is simply the comparison two values, more precisely, their mutual equality and its mathematical representation is: $P \iff Q$. It can be illustrated by "P equals Q" or mathematically $P \equiv Q$, which means: are P and Q the same.

> [!NOTE]- More in depth (example of different cases)
> This applies to both invalid and valid value types, both must be equal one to the other: 
> - P and Q are both _valid_ then $P \iff Q$ is valid
> - P and Q are both _invalid_ then $P \iff Q$ is valid
> - but if P is _valid_ and Q _invalid_, then $P \iff Q$ is invalid

#### Truth tables
Truth tables help us visualise all possibilities in assertions we stumble upon:

|$P$|$Q$|$P \land Q$|
|--|--|:-----:|
|F|F|F|
|F|V|F|
|V|F|F|
|V|V|V|
