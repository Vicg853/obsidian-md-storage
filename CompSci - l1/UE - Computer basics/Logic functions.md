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

