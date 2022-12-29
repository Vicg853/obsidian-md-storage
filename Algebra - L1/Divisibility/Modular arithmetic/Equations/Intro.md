Modular arithmetic, appart from being intriguing on itself, has its purpose: solving modular equations, which can lead us to solve normal equations, more specifically: $ax+by=c$ format equations, but well see that [[Solving ax+by=c|later]]. 

For starters, a modular equation, has a format of $ax\equiv c\ [n]$.

How to solve it: 

#### $a$ inversible in $n$
In this case, which means $a \land n = 1$, the solution, usually noted $S_E$, is simply defined by:
$$ãc+nk,\ k \in\Bbb Z$$

#### General case
If we don't have $a$ inversible in $n$, we must follow a different method to find things. We first must consider that if $a\land n \not | c$, there is no solution for this equation: $S_E = \emptyset$.

Otherwise, when $a\land n | c$, we first start by discovering three derivate variables: $a'$, $c'$ and $n'$. They all verify the following statement
- $a = a'(a\land n)$
- $c = c'(a\land n)$
- $n = n'(a\land n)$

Therefore, solving our equation, comes down to solving: $$a'x \equiv c'['n]$$
Which interestingly presents coprime $a'$ and $n'$ integers and therefore $a'\land n' = 1$, allowing us to solve it using the inversible method and at the same time the previous equation, as they share the same solutions: $S_E' = S_E$. 
