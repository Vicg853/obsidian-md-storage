Calculations cost us time and energy. Simplifying functions is essential on computer science, they allow us to solve problems, always with the best efficiency.

### Adjacent terms
It's when two conjonctive expressions only differ on one variable that has opposites on each side of the OR: $\overline a.b + a.b$. 

Cases like this can be simplified into removing the variable that has opposites on each sides. 
$$\overline a.b + a.b = b \cdot (\overline a + a) = b$$

You may also apply this in very complex expressions: 
![[Pasted image 20221104154811.png]]

### Karnaugh's table
#### Construction
This table helps us to simplify functions. They only accept disjonctive or conjunctive expressions.

To create it, we first identify the expressions [[Basic boolean expressions#Truthiness tables|truthiness table]] and from top to bottom index each element. We then format Karnaugh's table using the Boolean value's correspondant expressions in the following format: [[Pasted image 20221104160020.png |(hover me to see me)]] (see, we have for example $a = 0$, then its representation on K's table will be $\overline a$ and etc).

#### Simplification
The solutions in K's table, can be found by grouping adjacent ``1``'s in parallelogrammical forms, with a  variable count that are powers of 2 and finally, at least one of its ``1``'s must only belong to this group (as we may have many of them that share elements).

![[Pasted image 20221104161412.png]]


