Mathematical sets can be summarized with three main words: set, element and belonging (ensemble, élément and appartenance): consider $x$ an integer and $E$ a set, we note $x \in E$, which states the _element_ $x$ _belongs_ to the $E$ _set_. 

> [!INFO]
> A set can also be considered an element

> [!WARNING]
> Every set is an element, but not every element is a set. Take the previous statement as an example: we have $E$ that is both a set and an element at the same time, and $x$ which is simply an element.

There are two notations for sets:
- simple interval or listing declarations: ${1, 2, 3, 4, 5} \lor [0; 5]$
- or by equation assertion: lets consider a $P(x)$ and $E = \{\ x\ | \ P(x)\ \}$. This states that $E$ is defined by every $x$ for which $P(x)$ is true.

#### Set equality
Two sets are considered equal if every element of one exists in the other and vise versa.:  $$(E = {1, 2}, F = {1, 2}) \implies F = E$$

Along with this, we have three properties:
- For every set, let's say $E$, we have $E = E$, which is called reflexivity
- If we have two sets, let's say $E$ and $F$, where $E = F$ we have the called set symmetry
- We now consider three sets: $E$, $F$ and $G$. If $(E = F \land F = G) \implies E = G$. It is called transitivity
#### Set inclusion
We say that a set is included in another if for every of a sets content is included in the other: $(E = \{1, 2\}, F = \{1, 2, 3\}) \implies E \subset F$. Considering the last example, we can also say that $E$ is a proper subset of $F$.

We can consider the following statements: 
- for all intervals, let's take $E$ as an example, we have $E \subset E$
- if we have two subsets, let's consider $E$ and $F$ and $E \subset F, F \subset E$, then $E = F$
- We now consider three sets: $E$, $F$ and $G$. If$E \subset F, F \subset G$, then $E \subset G$


