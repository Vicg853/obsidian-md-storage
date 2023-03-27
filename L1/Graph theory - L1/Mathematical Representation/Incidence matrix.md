An incidence matrix represents a node's connection to a specific edge. Therefore, it isn't necessarily a square matrix, as it may have a different number of edges than the graph's node count. 

In other words, the matrix lines correspond to nodes and the columns, to a respective edge. Therefore, in a column where the lines $u$ and  $v$ have a one value, states that both these nodes are incident of the respective edge. 

Differently than other representation approaches, for this one, there are two possible ways to represent the data in the matrix: 
- in an oriented graph, by using three possible values to represent a connection: ``-1`` as the arc coming out of the respective node, ``0`` as the arc has no connection whatsoever with the respective node and ``1`` as the arc coming into the respective edge
- in an un-oriented graph, using two values as always: ``1`` edge is incident to the respective node and ``0`` if it isn't

It is interesting to note that, when we have two identical columns, we can certainly assume that there are double edges/arc for a certain node set.