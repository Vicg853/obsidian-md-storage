Apart from the basic Boolean operators, which are: ``NOT``, ``OR`` and ``AND`` (more on them with the [[Basic boolean expressions| boolean expression basics]]. They are very useful, as we can prevent from having to write long operations on paper, with ony basics one, instead we just use the operator.

Anyways, they have pretty similar properties to the basic ones, therefore, all theory on the basic one, as for example [[Basic boolean expressions#Morgan's rules| Morgan's rule]] should be applicable to some of those operators (maybe with some modifications).

#### Complete operators
A complete Boolean operator, is characterized by being writable using all three boolean basic operators. More specifically, they can be translated to a a Boolean expression which is composed by all three basic boolean operators.

#### List
A list with the most common ones

###### XOR
Noted $\oplus$ it can be translated to: "only one or the other, but not both". 
**$a \oplus b = \overline a \cdot b + a \cdot \overline b$**

He is: commutative, associative and complete.

###### NAND
It has no special notation and is simply **$\overline{a  \cdot b}$**. It can be translated to "not both at the same time".

He is simply commutative.

###### NOR
It can be translated to: "neither one neither the other" and has no special character for its representation, as it can be simply written as **$\overline{a + b}$**.

It is: commutative and complete