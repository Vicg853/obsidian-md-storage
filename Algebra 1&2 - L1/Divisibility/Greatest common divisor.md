Let consider we have two integers $a$ and $b$, their greatest common divisor (GCD), is the greatest integer that is both on $a$'s and $b$'s dividers sets. 

We note it: $a \land b$. 

The GCD can be explained mathematically with: consider $d$:
- $d\ |\ a \land b$, then
	- $d\ |\ a$
	- $d\ |\ b$


__$\mathscr{E.G.}$__ : $D(18) := \{\pm 1,\pm 2,\pm 3,\pm 6,\pm 9\}$ and $D(12) := \{\pm 1,\pm 2,\pm 3,\pm 4,\pm 6,\pm 12\}$ $$18 \land 12 = 6$$

#### Coprimes
If we have $a \land b = 1$, $a$ and $b$ are considered prime between them. 

In a more understandable way, we can say that we have an $a = d\cdot a'$ and $b = d \cdot b'$, where $d = a \land b$.

Having $a \land b = d = 1$ means both $a$'s and $b$'s common divisor is 1, therefore, therefore, they are either 
- two [[Algebra 1&2 - L1/Primes/Intro#Composed|composed integers]] that are prime between them;
- or two prime integers;
- or a prime and a composed integer.