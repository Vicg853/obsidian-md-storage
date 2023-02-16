We can also use Matrices to represent a Node's incident Edges/Arcs. Its called an incidence Matrix and differently to a normal [[L1/Graph theory - L1/Reprsentation/Intro#Mathematical representation| Graph Matrix]], it isn't symmetric as it has dimensions of $n\cdot m$.

#### Non oriented
In non-oriented graphs, each of the matrix's line represents a node and each column an Edge it is connected to, tho it is completely arbitrary the order used to note them.

Each column corresponds to a single incidence for a respective Edge: if an Edge is connected to both $u$ and $v$, their respective lines, will have 1 as value for the corresponding column used to represent this Edge.

#### Oriented graphs
The difference on oriented Graphs, is that the value can be either 0 or 1 (incoming Arc) or -1 (out-going Arc). 

