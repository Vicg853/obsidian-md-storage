Trees in summary, as defined by [[L1/Graph theory - L1/Trees/Intro| graph theory]], are a way of representing data, by using so called nodes (circles). These nodes are connected one to the other, but in such particular way, that a node can only be connected to a maximum of three other ones, without ever creating loops.

Therefore, they usually look like real like trees: a root, followed by branches, that branch over and over again. **On this course we are going to focus on infinite ramified trees** (a tree where each node contains a maximum of two children).

We are later also checking out binary search trees. 

#### Vocabulary
There are a few key vocabulary notions worth knowing when talking about trees in computer science:
- a _parent node_: a node's parent is his ascendant;
- a _child node_: a node's child is his descendent;
- a _internal node_: a node holding at least a single child
- a _external node_: a node holding no children (also known as a leaf node)
- a _simple node_: a node containing a single child
- a _full node_: a node containing both children
- a _full tree_ is the name given to a tree only containing full nodes, only excluding its leafs
- a _perfect tree_ differently than the definition given above, characterizes a tree with full levels, aside from the last one, where nodes will be placed to the foremost left
- a _deformed tree_ is the name given to a tree containing only simple nodes

#### Theorems
###### Full tree height to node count proportion
There are proofs that $\log_2 n\le h(B)\le n - 1$

###### Full tree node count
A full tree's node count corresponds to the following equation: $2^{h(B) + 1} - 1$

###### 

#### Algorithms
###### Traversal
There are three types of tree traversal: _prefixed_ (a procedure is performed on the current node before performing the same on the child nodes), _infixed_ (a procedure is called on the current node in between its execution on the left and right children) and _suffixed_ (the procedure is executed on the current node, after it being executed on both children) traversals, that come with their particular use cases. 

The most simple way of performing these algorithms, is by performing recursive procedure calls. For example, here we have the prefix algorithm applied as a display function: 
```pseudo 
prefix(r) 
Parameters: 
	r: node
{
	if (r != null) alors {
		display r.identifier
		prefixe(r.fg)
		prefixe(r.fd)
	}
}
```

It can also be done iteratively: 
```pseudo 
prefix(r) 
Parameters: 
	r: node
{
	Pile.pile(r)
	while(not Pile.empty()) {
		r = Pile.pop_top();
		if (r != null) alors {
			display r.identifier
			Pile.pile(r.left_child)
			Pile.pile(r.right_child)
		}
	}
}
```

###### Insertion
A simple insertion, inside a common tree, is performed by first asking for two nodes: one for insertion and the other as its future parent. We traverse the tree looking for a parent node and insert its new child under it. 

> [!caution] Insertion
> It is important to remember, that a node could be inserted as a an internal node's children, therefore, we need to also assure that the parent's replaced old child, is used as the new node's respective child.
> 
>Example a ``y`` node's left child ``z``, is replace by a ``x`` node, which should now contain ``z`` as it's left child

###### Optimized iterative traversal
Traversal without using neither recursive methods nor pile or queue structures
