Most matrices, can have an Identity product when multiplied to another matrix, which is called its "inverse".

Finding a matrices' inverse, consists in extracting a linear non-homogeneous system out of the current matrix's coefficients. We then it into a [[Crammer system|crammer system]], where all pivots column, have null elements appart from the pivot itself. 

This manipulation, should result in coefficients as the equation results, which can be translated into a matrix.

###### Example
Consider the A matrix, defined here:
$$A = \left(\ \begin{matrix}1 & 1 & -1\\ 1 & 0 & -1\\ -2 & 1 & -2\end{matrix}\ \ \right)$$

We can invert it with the procedure described above and applied here:
![[IMG_20230311_141501351.jpg]]

#### On 2 by 2 matrices
To find a matrice's inverse, there is a pretty simple method, that consists o finding this matrice's called determinant. When multiplying the matrix by its determinant, we successfully find its inverse. 

$$A = \left(\begin{matrix}a & b\\ c & d\end{matrix}\right)$$

Finding the determinant consists of 