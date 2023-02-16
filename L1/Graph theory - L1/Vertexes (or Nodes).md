A vertex, as already stated, is an element, which creates connections with other elements. It is commonly represented as a circle and an unique identifier: an integer, a letter, ...

A vertex's degree, is the total count of connections it holds to others, or even, to itself added to it. The sum of all of a graph's vertexes is equivalent to double its size (as in the edge count): $$\sum_{u \in V} d(u) = 2\cdot m$$

#### Neighbourhood
A Node's neighbourhood is(are) the other(s) Node(s) connected to it, which is mathematically defined as: for a node $u$, $v$ is it's neighbour if $\exists\ (u,v) \in V$. Actually, its not actually their neighbourhood that is being represented but more like, the Arcs/Edges that connected them to other Nodes.

For an non-oriented graph, a Node's neighbourhood is usually noted $\mathcal N(u)$. As for oriented graphs, the notation follows the Node's Arc set notation, using "+" and "-" [[Edges-Arcs#Arcs|as specified here]].

#### Adjacent list
The actual neighbourhood (and not through the usage Arcs/Edges), is represented as a list, e.g.: $\mathsf{list(}u\mathsf{)} = [v]$.

