A second order differential equation's homogenous form has a result $c=0$. But this is one of its characteristics. 

For our homogenous solution, we make the use of a very familiar equation format, the second degree polynomial equation, which is written using some of equation's elements: 
$$X^2+aX+b$$

We call it its characteristic polynomial and we note it $P(X)$.

###### Discriminant
For our homogenous equation's solution, we use the already known second degree discriminant, in a slightly modified format:
$$
\Delta = a^2 -4b
$$

Then:
- if $\Delta\gt0$, we have two solutions noted $r_0$ and $r_1$: $$r_{1,\ 2} = {{-a\pm \sqrt{\Delta}}\over2}$$
  Where $S_H=\{\ y: t\to \lambda e^{r_1t}+\mu e^{r_2t}\ ;\ \lambda, \mu \in \Bbb R \}$
- if $\Delta=0$, we have a single solution noted $r$: $$r = {-a\over2}$$
  Where $S_H=\{\ y: t\to \lambda e^{rt}+\mu t e^{rt}\ ;\ \lambda, \mu \in \Bbb R \} = \{\ (\lambda+\mu t)e^{rt}\ ;\ \lambda, \mu \in \Bbb R\}$
- if $\Delta\lt0$, we have two complex solutions noted $r_0$ and $r_1$: $$r_{1,\ 2} = {{-a\pm i\sqrt{|\Delta|}}\over2} = {-a\over 2}\pm i{\sqrt\Delta\over 2} = \alpha + i\beta$$
  Where $S_H=\{\ y: t\to (\lambda \cos(\beta t)+\mu \sin(\beta t))e^{\alpha t}\ ;\ \lambda, \mu \in \Bbb R \}$

