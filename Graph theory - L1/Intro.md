A graph is a data structure, used across a multitude of disciplines. 

Usually noted $G$, it contains two main set elements, noted $V$ and $E$: vertices and edges respectively; Its full form is noted $G = (V, E)$.

Edges are similar to points and vertices are the "paths" that connect them all together.
Vertices are noted as a set of two edges that are connected by the current edge.

##### Properties
- Not every edge is connected to every other one
- Some edges can be left alone (no one is connected to it)

##### Definition
A graph's "order" corresponds to its edge count and its size is its vertice/arc count.
This is applied for both arc-like or vertice-like graph.

##### Vertices type
_A loop_
_A multi-vertice_

##### Vertice and arc vocabulary
An edge is _incident_ to an arc/vertice, if it is one of it's extremities.
An arc _originates_ from an edge, if this edge is the first element of its set.

##### Graph types
_Simple graph_: is a graph containing only simple vertices: 
_Multi-graph_: is a graph containing at least a single looped vertice or multi-vertices

##### Vertice degree
$d(u) = |\delta(u)|$

##### Arcs
Arcs can be illustrated as oriented vertices, or vector-like vertices 