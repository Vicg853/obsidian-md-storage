An adjacence list, is simply a list, containing all of a respective node's neighbours. An actual list behaves the same for a certain node when alternating between oriented and un-oriented graphs. The only difference is that:
- in an oriented graph, if $u$ is present in $v$'s list, does not mean that $v$ will be in $u$'s list;
- in an un-oriented graph, if $u$ is present in $v$'s list, then $v$ is imperatively present $u$'s list.

Apart from that, we also have the following properties:
- A node will be present in its own list when it contains a loop to itself, therefore, we are talking about complex graph
- In an _non-oriented graph_, it is [[Known graphs#Connectivity|completely connected]] if none of the lists are empty (noted: $list(u) \not = []$).
  This does _not apply_ to _oriented graphs_ as an empty list can simply mean that a node does not have any outgoing arcs from itself and may only have incoming ones.

