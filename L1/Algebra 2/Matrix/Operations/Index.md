#### Matrice addition 
Matrix to matrix can only be performed between equally sized matrices. It is done by adding each of the matrices' coefficients directly one to each other:
$$A + B = (a_{ij} + b_{ij}) \in \Bbb M_{mn}(K)$$

Cross-matrice addition respect all commutativity rules.

#### Scalar multiplication
Matrices are allowed to be multiplied by scalars. For that, we simply multiply each of its coefficients by the desired scalar: 
$$\alpha A = (\alpha a_{ij}) \in \Bbb M_{mn}(K)$$

Scalar-matrix multiplication respect all commutativity rules.

#### Matrice multiplication 
The matrix-to-matrix operation that most differs from other mathematical elements operations is the multiplication. 

The first most important thing to note, is both matrices scaling: one of the matrix's column count must match the other's line count. 
The multiplication is then done, by summing up the product of one of each of a matrice column's elements by the other line's elements. In other words, consider $C = AB$: $$c_{ij} = \sum_{k=1}^{n} a_{ik}b_{kj}$$

Matrix-to-matrix multiplications are not necessarily commutative.

Interestingly $\exists AB = 0\ |\ A,B \not = 0$.

[[Powers]] also respect these rules and have some interisting and worth to be known behaviour.