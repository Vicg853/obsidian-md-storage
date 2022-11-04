Logic functions are Boolean expressions/evaluations, that produce a Boolean value. 

There are many ways to write and express these Boolean functions, some are easier and others.

#### Truthiness tables
A good way to visualize function results, are truthiness tables, they give us results for each of the function's variables and their variations.

Example [[tab-verit.png | hover or click.]]

#### Formats
Boolean functions have three main formats (all the listed patterns under here, are normal):
- _Disjonctive_ form: function elements are grouped into AND operator groups and then connected along with OR operators.
  $A . B\ +\ B . D + A . D$
- _Conjunctive_ form: elements are now grouped into OR operator groups and then connected along with AND operators. Note that, as it consist of OR operator groups, they must be surrounded by parenthesis. 
  $(A + B)\ .\ (B + D) . (A + D)$
- _Canonical_ form: each of the function groups, are composed of all of the function variables, that means, a canonical function is either also conjunctive or disjonctive. This means

#### Neutral and absorbant elements
###### AND operator
- $a + 0 = 0 + a = a$
- $a + 1 = 1 + a = 1$

###### OR operator
- $a . 0 = 0 . a = a$
- $a . 1 = 1 . a = 1$

#### Mathematical like properties 
###### Complementarity
**_OR_ operator**: $a + \overline a = 1$
**_AND_ operator**: $a \cdot \overline a = 0$

###### Distribution
$a \cdot (b + c) = (a + b) \cdot (a + c)$

###### Associativity
Associativity can be usually demonstrated and proven using truthiness tables.
**_OR_ operator**: $(a + b) + c = a + (b + c)$
**_AND_ operator**: $(a \cdot b) \cdot c = a \cdot (b \cdot c)$

###### Commutativity
Commutativity is when two Boolean variables can change their sides in the Boolean expressions (with the operator as an origin), without changing the expressions result:

**_OR_ operator**: $a + b = b + a$
**_AND_ operator**: $a \cdot b = b \cdot a$

#### Morgan's rules
Morgan's rules theorizes the development and factorization behaviours of Boolean statements negation.

**_OR_ operator**: $\overline{a + b} = \overline a \cdot \overline b$
**_AND_ operator**: $\overline{a \cdot b} = \overline a + \overline b$

The same applies to any other number of variables, e.g.: $\overline{a + b + c} = \overline a \cdot \overline b \cdot \overline c$