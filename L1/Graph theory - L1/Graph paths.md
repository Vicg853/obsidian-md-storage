There are also a set of definitions for observable patterns on a graph resembling the human definition of a path.

There are many different patterns, that will be listed here.

#### Chains
A chain is the most path resembling pattern: it defines a sequence of connected nodes, that usually colored to stand out from other nodes and edges.
![[Pasted image 20230222130606.png]]

##### Simple chain
A simple chain, is when in the defined sequence, no $(v_i, v_{i + 1}$ appears more than once in the chain sequence.

Note that, every simples chain, is at the same time necessarily an [[#Elementary chain|elementary chain]]. The same *does not* go the other way around. 

##### Elementary chain
An elementary chain relates closely to [[#Simple chain| simple chains]], but this time, a same $v_i$ can't appear more than once in a chain sequence.

#### Cycles
As the name states, some graphs present cycle-like patterns, allowing us to connect multiple nodes, until ending up into the same origin node. 

There are two main cycle types:
- normal cycle, were a same node is included twice in the defined chain sequence: $\exists u, v, w \in V\ |\ \ \ [(u,v), (w,u)] \in E$ or something similar
- elementary graph no node is present more than once in the defined chain sequence (apart from the start and end node).

When a graph lacks cycled behaviour, it is considered an acyclic graph.
![[Pasted image 20230224163852.png]]

#### Path and chains (in oriented graphs)
This section focus on oriented graphs, as arc make a graph behave differently compared to edges. 

Paths, are mostly the same as chains, the main difference comes with the fact that: in a chain, an arcs orientation is ignored. Therefore an oriented graph's chain won't follow an arcs direction. 
As for a path, it will respect all of a graph's arc's direction.

Oriented graph's chains' mathematical definition corresponds to: $P=v_1\dots v_k$ for $v_i \in V\ |\ \ \ [\ (v_i, v_{i+1}), (v_{i+1}, v_i)\ ] \in A$
As for a path, the notation changes at the end as only $(v_i, v_{i+1}) \in A$

##### Cycle and circuits
This notion also changes a bit on oriented graphs as:
- a _cycle_ corresponds to a **_simple chain_**;
- and a _circuit_ corresponds to a **_path_**

A new and key keyword for oriented graphs, appears when there is such a node whose path originated from, connects it to every other node present in the graph. This respective node, will be called the _root_.

