Some Graphs behave in particular ways.

#### Complementary graphs
These are Graphs that complement themselves as for Arc/Edge-wise. This can be easier understood as a Graph, which's complementary version, doesn't present its edges/arcs, but presents the edges/arcs missing in it.

Mathematically this can be noted: $G=(V, E)$ and $\bar G=(V, \bar E)$.
![[Pasted image 20230215095223.png]]

#### Regular graph
A regular graph behave in such a way that all his Nodes have the same degree. We also call them $\Delta$-regular, where delta is the shared degree number.

#### Complete and null graphs
In a complete graph every node is connected to every other possible nodes. All possibly existing edge, exists. 

Antagnostically, a graph where no connection exists, is called a Null graph: this graph does not feature any edges.

We can notice that a complete graph's [[#Complementary graphs|complementary]] version, is a null graph and it is the same thing the other way around.

#### Sub-graph
As its name state, an anologous notion for sub-graph, is a child graph, that contains its parent's nodes and at least some of its vertexes.

There are two types of subgraph's:

![[Pasted image 20230219210719.png]]
##### Straight away "sub-graphs"
The normal type, features all of its parent's nodes, but does not necessarily features all of its edges.

An example's and model mathematical notation can be: $\forall e=(u,v)\in E' \implies u, v \in V'$. 
As we can see: all edges composed by the two of a graph's distinct nodes, that are present in a sub-graph's edge list, assures that both those nodes will be present in the sub-graph's node list. But it doesn't actually assure that all of these nodes connection's exist

##### Induced sub-graphs
Differently that its normal version an induced sub-graph, has all of its parent's graph edges and nodes.

This can be mathematically stated as: $\forall u,v \in V'$ and $e = (u, v)\in E \implies e \in E'$. 
As we see, for all node included in the node sub-graph's node list, if there are edges in the graph's edge list, this edge will be included in the sub-graph's edge list. 

We also say that an induced sub-graph, is induced from its parent, by ${u, v, ...}$ nodes.

#### Cliques and anti-cliques
The [[#Sub-graph| Sub-graph]] and [[#Complete and null graphs]] notions are important for this section.

_A clique_, is a Graph's complete sub-graph. 
_An  anti-clique_, is a Graph's null sub-graph. Consequently, it becomes a Graph's null and induced sub-graph (there is no connection between this specific node set, therefore it is implicitly an induced sub-graph as their vertexes are necessarily null).

##### Coloration
A graph's anti-clique can also have a color based representation, hence the "graph coloration" label. 
![[Pasted image 20230220120249.png]]

When coloring anti-cliques, each one must have its own defined color and their respective nodes must be colored in it. 

##### Partition
Partition is the idea of finding multiple anti-clique patterns in a graph and splitting them with coloration and into sets. 
We have therefore the mathematical properties for two vertex sets: $V_i \cap V_j = \emptyset \forall i, j$ and $\cup_i\ V_j = V$.

#### Coupe
A coupe, starts by splitting a graph into two sub-graphs and therefore paying a closer attention to the incidences to a given or both parts: the edges/arcs coming in/out of this sub-graph, that don't belong to this sub-graph.

Consider $S$ one of $G$'s coupe, we note its incidence: $\delta(S)$
![[Pasted image 20230220123337.png]]

##### Bi-parted graph
When a graph's coupe incidence set considers all of its edges, we can assume it as a bi-parted graph and also observe that all of the other coupe's nodes will have a connection with the currently observed coupe.