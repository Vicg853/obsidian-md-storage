We can use an adjacence matrix and its indexes, to represent a graph. More specifically connections between two nodes (with their respective indexes being their indexes on the matrix).

When doing this, we are talking about a square matrix, and usually, also about a simple graphs. 
The behaviour slightly changes on oriented graphs, compared to non-oriented ones: 
- on an oriented graph, the matrix is not necessarily symmetric: an arc exists from node $u$ to node $v$, therefore $M_{uv} = 1$, but $M_{vu}$ will not necessarily be 1, based on the previous conclusion;
- as for an un-oriented graph, the matrix is necessarily symmetric: if $u$ and $v$ are neighbors, then both $M_{uv} = M_{vu} = 1$, as there is not such thing as a precise direction of their connection.
Oppositely, for both graph types, when a matrix's element $M_{uu} = 1$, we can assume that the node $u$ loops to itself.



