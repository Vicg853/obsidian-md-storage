As we are working with divisibility, we have some of its more complex rules, that can be applied to modular arithmetic:
- _reflexivity_: $\forall a \in \Bbb Z, a \equiv a\ [n]$
- _symmetry_: $\forall a, b \in \Bbb Z, a \equiv b \implies b \equiv a\ [n]$
- _transitivity_: $\forall a, b, c \in \Bbb  (a\equiv b\ [n], b \equiv c\ [n]) \implies a \equiv c [n]$, we can prove this using GCD (more specifically Euclid's algorithm) of $gcd(a, b)$ with $gcd(b, c)$


##### Addition and multiplication
We can remember of the divisibility rule: $d|c, d|c' \implies d|c+c'$ and $(d|c) \mathsf{or} (d|c') \implies d|c\cdot c'$, and try to interpolate it with modular arithmetic.

We note that it can also be applied to two congruent elements, for a same divisor:
$$\left.\begin{array}{r}
a \equiv b\ [n]\\
a' \equiv b'\ [n]\\
\end{array}\right\}\implies\left\{\begin{array}{l}
a + a' \equiv b + b'\ [n]\\
a\cdot a' \equiv b\cdot b'\ [n]\\
\end{array}\right.$$

To demonstrate both: 
1) $a + a' \equiv b + b'\ [n]$
![[Pasted image 20221228150302.png]]
2) $a\cdot a' \equiv b\cdot b'\ [n]$
![[Pasted image 20221228150607.png]]

The same logic can be followed for $a$ and $a'$, leaving us with $n|bb'$ and $n|aa'$ and therefore with $aa' \equiv bb'\ [n]$.

##### Powers and $\cdot c$
Based on the previous proofs, we can conclude that 
$$\begin{align}
a \equiv b\ [n] \implies ac \equiv bc\ [n]\\
a \equiv b\ [n] \implies a^k \equiv b^k\ [n]\\
\end{align}$$
