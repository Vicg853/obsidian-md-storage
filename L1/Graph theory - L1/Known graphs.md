#### Hamiltonien
There are two types of Hamiltonien patterns in a graph: 
- chain-like (as defined [[Graph paths#Path and chains (in oriented graphs)|here]]) patterns, where all nodes are present in the chain, exactly once: an elementary chain, but all without closing the path at beginning node
- and cycle-like (as defined [[Graph paths#Cycle and circuits|here]]) patterns with the main difference being: the cycle completes

A particularity about cycle-like Hamiltonien patterns, is that when removing any of it's edges, we end up with a chain-like Hamiltonien pattern.

#### Euclidian
A Graph manifesting such behaviour is called an Euclidian Graph and it is only possible if it's nodes have a pair degree.

In an Euclidian graph, it is possible to go cycle through all edges of the graph's edges (note that based on a cycle's properties: it will go through all edges, exactly once).

#### Chain graph
A chain graph, is solely composed of a chain and formed in such way.

#### Cycle graph
A cycle graph, is solely composed of a cycle and formed in such way.

It has an interesting property: it will always be 2-regular (as defined [[Particular graphs#Regular graph|here]]).

#### DAGs
A _directed acyclic graph_ is a graph containing no paths whatsoever and manifesting topological behaviour, in such way that all nodes, have arc pointing superiorly indexing nodes. 

![[Pasted image 20230224210624.png]]

#### Connectivity
A Graph's _connectivity_ is based on its property of having (or not) all its nodes connected together: none of its nodes is alone.
![[Pasted image 20230224213559.png]]

As for in an oriented graph, if every node pair manifests a chain, then the graph is characterised as a having  _weak connectivity_ and when it presents a path, then it is has _strong connectivity_. 
![[Pasted image 20230224213534.png]]

Note that, when talking about connectivity overall, we are also talking about a connectivity components: every graph, has connective sub-graphs. All the three above mentioned types of connectivity, are particularly composed by an only and  single connected sub-graph.

A non connected graph, actually has multiple connected sub-graph components.

In a non connected graph has two properties:
- a _maximal component_ has the particularity of being the key sub-graph that with a single connection, can break the current graph's connectivity;
- a graph's _connectivity maximum_ component, is the component, which's connectivity is the highest
![[Pasted image 20230224214441.png]]

