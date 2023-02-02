We can represent a grouping of subsets, in the following way: $\mathcal P(E)$.
For example: $$\begin{align}
E = \{1, 2, 3\} \\
P(E) = \{\emptyset, \{1\}, \{2\}, \{3\}, \{1, 2\}, \{2, 3\}, \{1, 3\}, \{1, 2, 3\} \}
\end{align}$$

> [!NOTE]
> $P(\emptyset) = \emptyset$

#### Complementarity
We call a complementary subset, the set of values, inside a set, minus the values of a subset from this initial set. It is noted $\mathcal C$. We translate everything mathematically to: $\mathcal C_EA = E \setminus A = \{x \in E / x \in A \}$.

We also note it $A^\mathcal C$.

Graphically this translates to: 
![[Pasted image 20221023202243.png]]

#### Complementary and relations
When we work with set relations, we are also mostly working with complementarity. 

Consider the following schema:
![[Pasted image 20221023203401.png]]
We therefore have the following properties:
- $(A^\mathcal C)^\mathcal C = A$
- $(A \cup B)^\mathcal C = A^\mathcal C \cap B^\mathcal C = E \setminus (A \cup B)$
- $(A \cap B)^\mathcal C = A^\mathcal C \cup B^\mathcal C = E \setminus (A \cap B)$ (remember that $A^\mathcal C$ includes the $B$ subset and vise versa !!)
- $E^\mathcal C = \emptyset$
- $\emptyset^\mathcal C = E$
- The following statement isn't true in this case, but we are supposing that if: $(B = A^\mathcal C) \iff (A \cap B = \emptyset\ \land \ A \cup B = E)$. This explained by, that if $A$ complementary, is also equal to $B$, it means that $A \land B$  are disjoint. Which means that their intersection is an empty set and $A$ or $B$ is equal $E$


 