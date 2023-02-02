A point's polar coordinate, noted $(x, y)$.

In a plan of center $O$, a couple $(r, \theta)$, where $r$ is the distance between the center and a point $M$ and $\theta$, $M$'s angle opening respective to the $x$ axis of the plan. This couple allows us to define:

$$\left\{\begin{array}{l}\ x = r\ \mathsf{cos}(\theta)\\ \ y = r\ \mathsf{sin}(\theta) \end{array} \right.$$

... a.k.a. $M$'s coordinates.

#### Dilation
Dilation happens, when a vector $\overrightarrow{OM}$ is multiplied by a $\lambda$ resulting in a $\overrightarrow{OM'}$. 
Therefore $\overrightarrow{OM'} = \lambda\ \overrightarrow{OM}$.

Depending on $\lambda$'s value, the dilation can have a different graphical behaviour:

![[Pasted image 20230102173055.png]]

#### Negative radius
Negative radius shouldn't actually exist in polar coordinates, but we can make them exist eventually, using a trigonometric property, such as the following example: for $M(-2, \theta)$
$$
\left\{\begin{array}{l}
\ x = -2\cos\theta\ =\ 2(-\cos\theta)\ =\ 2\cos(\theta+\pi)\\ 
\ y = -2\sin\  \theta\ =\ 2(-\sin\theta)\ =\ 2\sin(\theta + \pi)
\end{array}\right.
$$

Because remember from [[L1/Calculus 1/Derivation/Derivatives/Trigonometric functions|this]]: $\cos (x + \pi) = -\cos x$ and $\sin (x + \pi) = -\sin(x)$.

#### Pythagoras
The Pythagoras theorem actually comes from trigonometric properties:
- $r$ is the hypotenuse of the $\widehat{OxM}$ triangle, therefore: $r = \sqrt(x^2+y^2)$;
- As $r\cdot\cos\theta = x$, then $\cos\theta = {x\over \sqrt{x^2+y^2}} = {x\over r}$
- As $r\cdot\sin\theta = y$, then $\sin\theta = {y\over \sqrt{x^2+y^2}} = {y\over r}$