The label "diferencial homogenous associated function" method, is composed of two step: the first one $b(x)$ ($b$ as defined [[Calculus 1&2 - L1/Differential equations/First order linear/Intro#Solving|here]])  is swapped by $0$.

We end up with $y' = a(t)y$, which is labeled as a homogenous associated differential function.

We can compare $y$ to the exponential function, leading us to: $f'(t)=A'(t)e^{A(t)}=a(t)e^{A(t)}=a(t)y$, where $A$ is $a$'s primitive,

We can therefore, assume that for every differential associated function, one of our many solutions, can usually be: $$y = \lambda e^{A(t)}$$

The final solution is usually noted: $S_0 = \{y\ :\ t \to \lambda e^A(t)\ ;\ \lambda \in \Bbb R\}$

#### Second part
The second part allows us to find the solution for its entirety. We must start by finding lambda, which is currently unknown

###### Proof
![[Pasted image 20230108160427.jpg]]

###### Cauchy's problem
Solving a homogenous associated function, usually ends up connecting with [[Cauchy's problem]]:

###### Constant variation
We know that one of $y$'s solution, has a format of $\lambda + e^{A(t)} = k(t)\cdot z(t)$ and if we derive this equation (to find $y'$) we end up with a $(uv) = u'v+uv'$, therefore:
$$\begin{align}
y_0'(t)=k(t)\cdot z'(t)+k'(t)\cdot z(t)\\
\ \ \ \ =k(t)\cdot z'(t)+k'(t)\cdot z(t)\\
=k(t)\cdot(a(t)\cdot z(t))+k'(t)\cdot z(t)
\end{align}$$

> [!NOTE]
> $A$ is $a$'s primitive
> $k(t)\cdot z'(t)+k'(t)\cdot z(t) = \lambda\cdot a(t)e^{A(t)}+\lambda'\cdot e^{A(t)}$

See something familiar? The same format as the initial $y'$, which allows us to assume that $b(t) = k'(t)\cdot z(t)$.
Therefore we have as a solution: $$S= \{\ y: t\to k_0(t)\cdot z_0(t)+\lambda z_0(t)\ ;\ \lambda \in \Bbb R\ \}$$ 
