To go on with this, be sure to have a good understanding of [[Intro|boolean logic basics]] and [[Vocab|basic vocabulary]]. 

#### Syllogism
With Syllogism (or as also called direct thinking), we simply follow a direct flow of thinking, going through each of the statement's steps and proving each one at its time.

#### Case separation (or case disjunction)
As the name explains, we split the statement into steps and solve them each in its isolated space and then we join everything together for a final conclusion.

It is useful with absolute values for example, when the equation must usually be solved with two separate point of views: when $x \lt 0$ and $x \ge 0$. 

#### Contrapositive
Proving by contraposition is done by inverting and showing a statement is false. Using Boolean logic this translates to converting $P \implies Q$ into $\lnot Q \implies \lnot P$ and demonstrating this translated statement is valid.

Consider this class' example: 
![[Pasted image 20221020225413.png]]

#### By absurd
When reasoning by absurd we follow an absurd logic which concludes into a called contradictory statement.

Consider the following example:
![[Pasted image 20221020230132.png]]

#### By counterexample
A counterexample is when you find an only case in a $\forall x \in A$ assertion format, where it does not work. 

This translates mathematically into: $$\begin{align} 
\forall x \in A
\\ \exists\ x_0 \in A, \lnot P(x_0)
\end{align}$$

#### By recursivity
We recursively demonstrate a statement, by creating an introduction axiom, which we suppose is "strictly true" (usually by proving a mathematical equation against 0 or 1) and then a second axiom where we usually prove the statement basing ourselves from what has been found in the introduction and therefore confirming what was supposedly true.

This way we will have stablished the following mathematical statement:

1)$\ \ P(0)$ is true$._\text{(introduction axiom)}$
2)$\ \ n \in \Bbb N, (P(n) \implies P(n + 1))$$._\text{(development axiom, or "hérédité" in French)}$
therefore $P(n)$ is true $\forall \ \Bbb N$

Consider the following example: 
![[Pasted image 20221022140940.png]]

#### Necessary and sufficient conditions
We have $P$ and $Q$:
- P is a sufficient condition for Q: $P \implies Q$, as if the previous and $P$ are true, then $Q$ is true too;
- P is a necessary condition for Q: $Q \implies P$, as if $Q$ is true, then for $\lnot Q \lor P$ to be true, $P$ must be true;
- P is sufficient and necessary for Q: $P \iff Q$, $P$ is necessary for $Q$ and $P$ sufficient for $Q$

Consider the following example: 
![[Pasted image 20221022144137.png]]

Here we have $P$ equals to the $n = 0 \lor n = 1$ statement and $Q = n^2 - n$ one. We have proven that $\lnot P \lor Q$, or, that $P$ is sufficient for $Q$, as if $P = true, \lnot P = false$ then $P$ is sufficient for $Q$ to be true.
At the same time, $\lnot Q \lor P$, or, that $P$ is necessary for $Q$, as if $Q = true, \lnot Q = false$ therefore $P$ is a must as $Q$ is true.