A graph is a data structure, used across a multitude of disciplines. 

Usually noted $G$, it contains two main set elements, noted $V$ and $E$: vertexes and edges respectively; Its full form is noted $G = (V, E)$.

Vertexes are similar to points and edges are the "paths" that connect them all together and Edges can be noted as a set of two vertexes which are connected by it.

Note that, not every vertex is necessarily connected to every other vertex, and neither are them necessarily connected to anyone.

We also have some special Graph behaviour sometimes, which are stated [[Particular graphs|here]].

##### Vocabulary
- "order": a graph's vertex count
- "size": a graph's edge count
- In a "simple graph" each vertex has a single connection to another vertex ([[Pasted image 20230213140106.png|e.g.]])
- Differently in a "multi-graph" we may (as well as we may not) have multiple connections between two vertexes ([[Pasted image 20230213140020.png| e.g.]])

##### Notation
A graph's:
- order is usually notated $n$ and is an element of the graph's $V$ set;
- size is usually notated $m$ and is an element of the graph's $E$ set;

##### Components
A Graph is mainly composed of a couple elements:
- [[Vertexes (or Nodes)]]
- [[Edges-Arcs| Edges and Arcs]]

##### Size limits
An un-oriented graph's max size can be discovered using its order in the following operation: 
$${n(n-1)}\over2$$ 
As for oriented graph's max size can be discovered using its order in the following operation: 
$$n^2$$