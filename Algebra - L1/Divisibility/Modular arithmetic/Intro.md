Modular arithmetic allows us to closely study divisibility rules and properties, mainly by introducing us to a specific and concise syntax:
$$a \equiv b\ [n]$$

This expression states that: for $n$ to be a valid dividend, we must subtract $b$ from $a$, therefore that $b$ is actually $r$ (rest).

As for the written form, we say that: $a$ and $b$ are "congruent" or "not congruent" in modulo $n$.

### Residue
The modulo residue, is $r = b$ and it can be expressed in the following way: $a\mod n$. 
The residue, by convention, is usually $r \in [0, n - 1]$ ($a \equiv r\ [n]$).

Although, it must be noted that $r$ (or $b$), could actually be higher than this and that this interval exist, to narrow the possibilities and therefore reduce complexity.

### Properties
- $a \equiv b\ [n] \iff a \mod n = b \mod n$. 
  As if we respect the interval, we should usually have $b \lt a, b \gt n$ therefore $a \mod n = a - k \cdot n = r = b = b mod n$
- $a \equiv 0\ [n] \iff n\ |\ a$
- $a \equiv b\ [n] \iff -a \equiv -b\ [n]$
- $a \equiv b\ [0] \iff a = b$ as $a = k \cdot 0 + b$ 
- $a \equiv b\ [1]$ is always true as $\forall a,b \in\Bbb N \implies \{(1 | a, q | b), 1 | a - b\}$
- $\forall k_1, k_2 \in \Bbb Z, a\equiv b\ [n] \iff a + k_1\cdot n \equiv b+k_2 \cdot n\ [n]$

And [[Complex properties|here]] we have some more complex properties.

### The big link
One of the biggest reasons of modular arithmetic and its derivatives, is to solve the famous double variable equation $ax+by=c$, creating a sure and exact method, instead of using systems, which can be arbitrary.