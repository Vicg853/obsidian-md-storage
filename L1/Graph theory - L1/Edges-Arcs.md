Edges as well as Arcs, are the connections created between two edges as stated before. They are commonly represented as a single line, going from a point from another.

Why two variants? Edges, correspond to an non-oriented connection, represented a simple line connecting two nodes. Arcs oppositely, have an orientation, they are represented similarly to vectors and define a strict direction. Hence a graph's adjectives: oriented graph and non-oriented graph.
They can both be called "_incident_" to a respective Node they are connected to.

A vertex's incident edge set is noted $\delta([vertex])$

### Edges
As stated, an Arc is one of the main characteristics of an non-oriented Graph. 

### Arcs
As stated, an Arc is one of the main characteristics of an oriented Graph. Their connections from now on, impose a precise direction, from a Node $u$ to its neighbour $v$. 
They are graphically represented as a Vector.

Therefore, every Arc has an _initial extremity_ (it's _origin_, going out of an $u$ Node) and a _final extremity_ (it's _destination_, going in a $v$ Node).

A Node's initial incident Arcs are noted $\delta^+([node])$ and all final incident Arcs are $\delta^-([node])$.
A Node's initial and final degree logic and notation behaves equally.

###### Looped arc
We consider an arc looped when it both originates and incides the same node.

It is usually noted with a set containing two times the same vertex: $e = (u, u)$ and ressembles to this:
![[Pasted image 20230213140143.png]]