A tree is defined as an acyclic and connected (it does not have any lose nodes) graph. On the opposite a forest, is a non connected graph, which's sub components compose a tree.


#### Vocabulary
- ``knot``:  is a tree's node
- ``leaf``: node with a degree of one
- ``internal leaf``: is a tree's node whose's degree is superior to 1 
- ``branch``: a tree's edge

#### Properties

##### Partitionning
Is bi-parted (remember that a graph can only be [[Particular graphs#Bi-parted graph|be bi-parted if]] it does not contain any un-even cycles, and tree's don't even have cycles for starters).

##### Edge count
It contains exactly ``n - 1`` edges. 

As a tree is a fully connected graph, it has at-least ``n-1`` edges and a acyclic graph, has at most ``n-1`` edges. 

Therefore, a tree, being constrained by both rules, must have ``n-1`` edges.

##### Tree degree
A tree's degree is $\sum^n_{u=1} d(u) = 2\cdot (n -1) \gt 2\cdot n$

#### Graph properties
As for graphing properties, trees englobe a bunch of them: they are a graph's minimal representation, as removing a single link would break conex-graph properties.
Adding a single new connection, creates a new and only cycle (an only, as in a tree, two nodes, that aren't connected directly, have an only and single chain linking them).

