Matrices are mathematical data structures allowing us to store multiple numbers together. 

Their inner content, is defined in the $\Bbb K$ definition body (containing $\Bbb R$ and $\Bbb C$). 
We also call it's elements "coefficients" and they can be retrieved by specifying its coordinates in such way: $A_{ij}$ (where $A$ is a matrix defined in $\Bbb K$).

We usually also state a matrix's elements using the matrix's name lower-case notation, e.g.: $A$'s coefficients can be noted $a_{ij}$.

Apart from the contents of this file, there are some other things worth noting about matrices:
- The [[Identity matrix]];
- A matrix's [[L1/Algebra 2/Matrix/Inverse|inverse]];
- The relationship with [[Linear equation rel.|linear equations]];
- Matrix [[Index| operations]].

#### Definition sets
We can also create and represent matrices in a matrice representation set. They are stated in the following format:
$$
M_{mn}(\Bbb K)
$$

We can also talk about: $M_{n}(\Bbb K)$ for square matrices with $n$ coefficients.

#### Basic matricial properties

##### Whole matrix's value
We say that two matrices are equal if, first of all they have the same dimensions and all its coefficients are equal one to the other. In other words consider $A, B \in M_{mn}(\ \Bbb R\ )\  |\ \ (\forall\ i,j \in \{1, \dots, m\} \times \{1, \dots, n\}\ \ A_{i, j} = B_{i, j})  \implies A = B$

##### Null matrice
A matrix is considered null, when all its coefficients are null.

#### Special matrices
We have some special and "commonly seen" matrices, that are worth stating:
- line matrice, containing a single line and multiple columns
- the column matrice, which oppositely to the previous one, contains a single column with multiple lines
- the square matrix as previously stated and defined
- the superior and inferior triangle matrices
	![[Pasted image 20230410153051.png]]![[Pasted image 20230410153111.png]]
- the diagonal matrice which has null coefficients all over it with the exception of its diagonal members ($\forall i \in n, A_{ii}$) (only works on square matrices)
- the identity matrice, which is similar to the diagonal matrice, but with diagonal members imperatively equal to $1$
- (a)symmetric square matrices, where its diagonally symmetric coefficients are equal and respectively different for an (a) one 
	![[Pasted image 20230410154334.png]] ![[Pasted image 20230410155020.png]]