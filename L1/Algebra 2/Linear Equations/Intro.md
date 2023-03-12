Linear equations system, is defined by a set of $n$ variable equations. 

It following notation, is used to define and list this set:
$$\left\{\begin{array}{c}
a_{11} x_{1} & + & a_{12} x_{2} & + & \dots & + & a_{n} x_{1n} & = & b_1 \\
a_{21} x_{1} & + & a_{22} x_{2} & + & \dots & + & a_{n} x_{2n} & = & b_2 \\
\vdots & \ & \vdots & \ & \ddots & \ & \vdots & \ & \vdots \\
a_{m1} x_{1} & + & a_{m2} x_{2} & + & \dots & + & a_{mn} x_{n} & = & b_m \\
\end{array}\right. $$

Where: 
- $m$ is a set's respective set's row index
- $n$ is a set's respective column index
- $a_{ij}$ are the equations' coefficients
- $x_j$ are the equations' unknowns
- $b_i$ are each respective equation's result

#### Matrix
Linear equations are also strongly tied to [[L1/Algebra 2/Matrix/Intro|matrices]] and can even be [[Linear equation rel.|represented as matrices]] (they usually separated into three matrices: a coefficients matrix, a unknowns matrix and a results matrix).

### Core elements and concepts
#### Pivot
A pivot, is the first non null element of a matrice's line. 

In some cases, we can see each of a system's line's pivots, behave in a certain special way, such on a crammer system, where each pivot

#### Homogeneous system
A homogeneous system, is when all equations' results are null

#### Compatibility
A system, is defined as compatible, when there is a solution for it. When a solution cannot be found, it is called an incompatible system, as its equations don't relate to each other.

#### Rank
When transforming a system from another form into an [[#Homogeneous system|homogeneous form]], we can find the so called system's "rank". 

The rank corresponds to the count of unknown elements present in it.

The rank allows us to find other things, such as: the [[#Solution dimension|solutions dimension]]s. 

The same can be found for [[L1/Algebra 2/Matrix/Intro|matrices]], when finding its associated [[L1/Algebra 2/Matrix/Rank|homogeneous system]].

#### Solution dimension