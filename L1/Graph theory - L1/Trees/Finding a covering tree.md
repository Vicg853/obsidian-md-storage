As defined [[Particular graphs#Covering tree| here]], a covering tree is a graph's sub-graph, in tree format. It can be found by using a specific algorithm, that goes through the graph in depth and verifies that with each iteration, a cycle isn't created for a certain node/edge.

![[Pasted image 20230326225633.png]]

This happens because, when going through a graph, we usually go through each-and-all nodes, without revisiting them. Consequently we end with an acyclic fully connected graph, a.k.a. a tree.