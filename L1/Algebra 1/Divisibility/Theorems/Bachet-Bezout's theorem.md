Bachet-Bezout states that $au + bv = a \land b$.

Moere specifically $a$ and $b$'s GCD, will be equal to $a \cdot u$ plus $b \cdot v$, where $u, v, a, b \in \Bbb N$, for a certain $u$ and $v$. 

### Properties
Consider $E$ the solution set of a Bachet-Bazout's identity. The solutions in $E$ will always be positive and $E$ itself will never be an empty set.

### Finding $u, v$

###### Example
![[Pasted image 20230118152015.png]]

### Proof
Bachet-Bezout used the following demonstration for its theorem: 
1) First, he proves that E will never be an empty set and that the solutions inside of this set will always be positive integers
![[Pasted image 20221225164339.png]]

2) He proves that there there exists an integer $d$ for all $a \land b$, by demonstrating that $a \land b$ divides a $d$. 
   Where $d = au + bv$:
![[Pasted image 20221225164601.png]]

3) Based on the previous statement, that this $d$ divides both $a$ and $b$ (the same logic is followed for both integers):
![[Pasted image 20221225164717.png]]

4) Based on the previous demonstrations, he finally assumes that $d \in D(a) \cap D(b)$, which means it present in both $a$'s and $b$'s divisors set, while it and its modulus being inferior or equals to $a \land b$.
	Leading us to the following expression $a \land b\ |\ d$ and $d = a\land b$.
![[Pasted image 20221225165431.png]]