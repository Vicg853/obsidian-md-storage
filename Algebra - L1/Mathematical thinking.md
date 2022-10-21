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
Demonstrating by recursivity consists of trying to prove a statement, by first initializing it (usually proving it by 0) and then demonstrating by an equations development, that this statement recursively works on any following case.

Consider the following example: 