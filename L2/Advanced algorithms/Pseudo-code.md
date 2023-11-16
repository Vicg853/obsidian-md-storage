Pseudo-code is a writing convention (just as programing languages), that dictate a common way of giving algorithmic instructions.

For its "global" format, algorithms can be shared without having to deal with language specific barriers.

Sadly, until today, there is not a written convention, defining its syntax and here, we are going to inspire ourselves from the book “Algorithmique” (Dunod's edition), written by e Cormen, Leiserson, Rivest and Stein.

#### Syntax
(Every element put within ``[]`` under this heading is an element to be replaced by pseudo-code compatible syntax)

###### Block definition
We open a block using ``{`` and then close it with a corresponding ``}``.

###### Numerable loops
These are the kind of loops usually containing a know iteration count (mostly know in programing languages as a ``for`` loop).

_English_: 
- ``for [element] in [enumerable]``; 
- ``for [element] from [enumerable start] to [enumerable end]``

_French_: 
- ``Pour [element] dans [enumerable]``;
- ``Pour [element] allant de [enumerable start] à [enumerable end]``.

###### Conditions
Instruction blocks that are executed only if a certain condition is met:

_English_:  ``if ([condition]) then { [instruction] } else { [intruction] }``

_French_:  ``Si ([condition]) alors { [instruction] } sinon { [intruction] }``

###### Procedures result
To signal a procedure's return we may use: 

_English_:  ``return ([element])``

_French_:  ``retourne ([element])``

###### Suffixed un-enumerable loop
It consists of an instruction loop, ran based on a condition. But this one differs from its [[#Un-enumerable loop| brother]], as instructions are performed before a condition check. This therefore can cause a key event: instruction are ran once at the start independently. 

_English_:  ``Repeat { [instruction] } as long as ([condition])``

_French_:  ``Repeter { [instruction] } jusqu'à ([condition])``

###### Un-enumerable loop
It consists of an instruction loop, ran based on a condition, commonly used in cases where the iteration count is unknown:

_English_:  ``while([condition]) { [instruction] }``

_French_:  ``Tant que ([condition]) { [instruction] }``

###### Data manipulation and comparison
- To indicate a data affectation or modification we use the ``=`` sing
- As for data parity we use the ``==`` (double ``=``) sings
- And for imparity $\not=$ (crossed ``=`` )
- For scale comparison the usual mathematical symbols can be used: $\le, \lt, \gt, \ge$
- Boolean algebra is also accepted with the use of the ``and``, ``or`` and ``not`` words
- An element sequence is done by using opening `[` and closing `]` (brackets) next to the set and then specifying the sequence's index is being accessed. 
  
  Example: ``A[i]`` where `A` is a sequence
  
  (single point where `[ ]` are actually pseudo-code, a.k.a. we are actually talking about pseudo-code applications of the ``[ ]``)
- Complex data structures' fields, such as sets' fields, are accessed by placing a point between the child data's denominator and the parent's one
  
  Example: ``A.b`` is the same as, the sub-data-field ``b``, under the data set ``A``