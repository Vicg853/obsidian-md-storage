Trees:

Forest: 

#### Vocabulary
- ``knot``:  is a tree's ndoe
- ``feuille``: node with a degree of one

#### Properties
- it is bi-parted

A tree is a connex graph (all its nodes are connected to each other) and at the same time, a non-cyclic simple non-oriented graph. Based on these observations, we can see that:
- it has ``n-1`` links 
- it is bi-parted, as a graph only can't be bi-parted if it has an uneven cycle (which a tree doesn't even have)
- A tree's degree is $\sum^n_{u=1} d(u) = 2\cdot (n -1) \gt 2\cdot n$

#### Graph properties
As for graphing properties, trees englobe a bunch of them: they are a graph's minimal representation, as removing a single link would break conex-graph properties.
Adding a single new connection, creates a new and only cycle (an only, as in a tree, two nodes, that aren't connected directly, have an only and single chain linking them).

