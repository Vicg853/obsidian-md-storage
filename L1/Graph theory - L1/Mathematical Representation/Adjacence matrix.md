We can use an adjacence matrix and its indexes, to represent a graph. More specifically connections between two nodes (with their respective indexes being their indexes on the matrix). 

When using matrix for this approach's purpose, we will always be talking about a square matrix, containing two values: 1, for when a connection exists between two nodes and 0 when it doesn't.

But, this approach's matrix can have different behaviour depending on the graph type where studying:

##### Un-oriented
In an un-oriented graph, the matrix will always be symmetric, as when using edges, if $(u, v)$ exists then $(v, u)$ necessarily exists.
Therefore the matrix will contain both indexes $M_{uv} = M_{vu} = 1$.

A matrixe's [[Trace|trace]] being null, dictates that the graph represented by it is of simple nature, or in other words, does not contain any loops (a node connecting to itself), as $\forall u \in V | M_{uu} = 0$ which means, that there are no edges connecting to themselves.
##### Oriented graph
Here, the representation changes as the matrix will not necessarily be symmetric, because $(u,v)$'s existence does not imply $(v,u)$'s one. 
Therefore the matrix will contain $M_{uv} = 1$, but not necessarily $M_{vu}\ ?= 1$.
When doing this, we are talking about a square matrix, and usually, also about a simple graphs.

As already kinda explained, links between a node $u$ to a node $v$ in a respective order represent an arc going in this respective "direction" (e.g.: index $uv$, or $wu$ represents respectively an arc coming from $u$ going to $v$ and another from $w$ to $u$). 
In other words, we first read the line, which corresponds to the node which the arc comes out from and then the columns, which corresponds to the node the arc goes into.

Just like for un-oriented graphs a trace of 0, represents a simple oriented graph, a.k.a. no looped arcs.



