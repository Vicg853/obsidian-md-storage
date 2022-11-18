Logic functions are Boolean expressions/evaluations, that produce a Boolean value. We usually don't write down Boolean expressions all alone, they're usually written in a function format, similar to mathematical functions.

#### Truthiness tables
A good way to visualize function results, are truthiness tables, they give us results for each of the function's variables and their variations.

Example [[tab-verit.png | hover or click.]]

#### Formats
Boolean functions have three main formats (all the listed patterns under here, are normal):
- _Disjonctive_ form: function elements are grouped into AND operator groups and then connected along with OR operators.
  $A . B\ +\ B . D + A . D$
  > [!FACT] 
  > All it's terms, in a truthiness table will only have one match for the value ``1`` (all others will be ``0``)
  
- _Conjunctive_ form: elements are now grouped into OR operator groups and then connected along with AND operators. Note that, as it consist of OR operator groups, they must be surrounded by parenthesis. 
  $(A + B)\ .\ (B + D) . (A + D)$
    > [!FACT] 
    > All it's terms, in a truthiness table will only have one match for the value ``0`` (all others will be ``1``)
- _Canonical_ form: each of the function groups, are composed of all of the function variables, that means, a canonical function is either also conjunctive or disjonctive. This means
  > [!TIP]  TIP: verification
  > In the canonical form more precisely, one of its single pieces, can be represented as expressions containing $2^{N - n}$ (where $N$ is the number of variables present in this expression and $n$ the number of term in the non converted piece).

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