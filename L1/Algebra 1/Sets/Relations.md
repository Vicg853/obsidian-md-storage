#### Subsets
We say that a set is included in another if for every of a sets content is included in the other: $(E = \{1, 2\}, F = \{1, 2, 3\}) \implies E \subset F$. Considering the last example, we can also say that $E$ is a proper subset of $F$.

We can consider the following statements: 
- for all intervals, let's take $E$ as an example, we have $E \subset E$
- if we have two subsets, let's consider $E$ and $F$ and $E \subset F, F \subset E$, then $E = F$
- We now consider three sets: $E$, $F$ and $G$. If $E \subset F, F \subset G$, then $E \subset G$

You can also see subsets with more details [[Subsets|here]].

#### Set equality
Two sets are considered equal if every element of one exists in the other and vise versa.:  $$(E = {1, 2}, F = {1, 2}) \implies F = E$$

Along with this, we have three properties:
- For every set, let's say $E$, we have $E = E$, which is called reflexivity
- If we have two sets, let's say $E$ and $F$, where $E = F$ we have the called set symmetry
- We now consider three sets: $E$, $F$ and $G$. If $(E = F \land F = G) \implies E = G$. It is called transitivity

#### Set reunion
We can state a reunion of sets, that is, we are considering value, on both sets: $E \cup F = \{x |x \in E \or x \in F\}$.

For set reunions we have the following properties to keep in mind:
- $F \cup E = E \cup F$
- $(F \cup E) \cup G = F \cup (E \cup G)$
- $E \subset E \cup F$
- $E \cup E = E$
- $F \cup \emptyset = E$

#### Set intersection
WE can state a set intersection, that is, we consider values that belong both at the same time to two stated sets: $E \cap F = \{x | x\in E \land x\in F\}$

Keep in ming these properties: 
- $E \cap F = F \cap E$
- $(F \cap E) \cap G = F \cap (E \cap G)$
- $E \cap F \subset E$
- $E \cap E$
- $E \cap \emptyset = \emptyset$

If the intersection of twos sets, is an empty set, then we can state that both sets are disjoint: they don't have any intersection. 
Graphically this translates to: 
![[Pasted image 20221023194749.png]]