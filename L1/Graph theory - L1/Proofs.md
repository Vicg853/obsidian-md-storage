Here are some proofs to be considered and that provide an explanation to certain Graph behaviours:

#### Pigeonhole principle
The pigeonhole principle, states that, if we have $n$ pigeons that my be inside $m$ boxes (where $n\le m$), we will necessarily have one box, containing more than one pigeon. 

This relates to graph in the node and vertex count properties. More specifically, we are talking about simple undirected graphs with this proof. 

Considering a graph, with $n$ vertexes, we will necessarily have at least two vertexes, with the same degree: we have $n-1$ possible degree's, ranging from $0$ to $n-1$ (a vertex can't be connected to itself). The use of all these possible degrees, is actually impossible, as: if we have a vertex with a $0$ degree we can't have a second one with $n -1$ degrees, which will actually have $n-2$. 
The same happens the other way around: with the absence of $0$ degree vertexes, we will have at least two degrees with the same degree count of $1$.

And this can all be simply summed up to: we have $n-1$ different degree possibilities, which must be split between $n$ different vertexes. Therefore, we don't have enough degrees to split between them, without at least two of them sharing the same.

