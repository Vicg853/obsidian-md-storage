We are now interested about how we can make these graphs "physical": how to store in memory (computers), how to structure it mathematically, etc.

We can mathematically represent a Graph using [[L1/Algebra 2/Matrix/Intro|matrices]], with a $n\cdot n$ dimension, whose elements have a value of either 1 or 0.

There are different approaches to represent a graph using them: 
- An [[Adjacence matrix|adjacence matrix]], where each coordinate represents connected nodes using indexes (e.g.: if the nodes 1 and 2 are connected, then the element $M_{12} = 1$)
- A [[Adjacence list|adjacence list]], containing a node's neighbours
- An [[Incidence matrix|incidence matrix]], where each coordinate represents that an $u$ node has a $x$ edge incident to it (e.g.: the edge represented in an $i$ column is incident to the node $1$ if the matrix element $M_{1i} = 1$)
- Object, which is good for object oriented approaches, where each of the graph's elements, will be represented as a different object

##### Properties
There are some properties we can easily observe using matrices:
- if there are no loops, the matrix diagonal values will be null

#### Complexity
Complexity is a very important matter when studying graphs. We may not perceive as humans, the time and algorithms we use to check two Node connection for example. But in virtual environments, it becomes obvious, how much some procedures can be time expensive.

Here are some useful time complexities:

