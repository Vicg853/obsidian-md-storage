A graph is a data structure, used across a multitude of disciplines. 

Usually noted $G$, it contains two main set elements, noted $V$ and $E$: vertexes and edges respectively; Its full form is noted $G = (V, E)$.

Vertexes are similar to points and edges are the "paths" that connect them all together and Edges can be noted as a set of two vertexes which are connected by it.

Note that, not every vertex is necessarily connected to every other vertex, and neither are them necessarily connected to anyone.

##### Vocabulary
- "order": a graph's vertex count
- "size": a graph's edge count
- In a "simple graph" each vertex has a single connection to another vertex
- Differently in a "multi-graph" we may (as well as we may not) have multiple connections between two vertexes

#### Vertexes (or nodes)
A vertex, as already stated, is an element, which creates connections with other elements. It is commonly represented as a circle and an unique identifier: an integer, a letter, ...

A vertex's degree, is the total count of connections it holds to others, or even, to itself added to it.

#### Edges / Arcs
Edges as well as Arcs, are the connections created between two edges as stated before. They are commonly represented as a single line, going from a point from another.

Why two variants? Edges, correspond to an non-oriented connection, represented a simple line connecting two nodes. Arcs oppositely, have an orientation, they are represented similarly to vectors and define a strict direction.
Hence a graph's adjectives: oriented graph and non-oriented graph.

Both of them anyway, have two connections: one is the _incident_, therefore comes int a node at this point and an _originated_, which comes out of a respective edge.

###### Max size
An un-oriented graph's max size can be discovered using its order in the following operation: 
$${n(n-1)}\over2$$ 
As for oriented graph's max size can be discovered using its order in the following operation: 
$$n^2$$

###### Looped arc
We consider an arc looped when it both originates and incides the same node.