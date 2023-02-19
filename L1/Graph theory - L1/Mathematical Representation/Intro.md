We are now interested about how we can make these graphs "physical": how to store in memory (computers), how to structure it mathematically, etc.

#### Mathematical representation
We can mathematically represent a Graph using [[L1/Algebra 2/Matrix/Intro|matrices]], with a $n\cdot n$ dimension, whose's each element has a value of either 1 or 0 and state if it exist a connection between the two Nodes with the respective value indexes. 
E.G.: a connection between two Nodes, such as $u$ and $v$, is represented by $M_{uv}$

##### Properties
There are some properties we can easily observe using matrices:
- if there are no loops, the matrix diagonal values will be null

#### Complexity
Complexity is a very important matter when studying graphs. We may not perceive as humans, the time and algorithms we use to check two Node connection for example. But in virtual environments, it becomes obvious, how much some procedures can be time expensive.

Here are some useful time complexities:

