Until now, we've only studied [[Circuits|combinational circuits]]: a simple function, with a standard input and output, nothing less, nothing more. Although these are the base for other circuits, they are fairly limited. 

Hence the existence of the called Moore machines (or temporal circuits, or non-combinational circuits), that consider previous inputs (or time) aside from standard inputs.

When crafting temporal circuits as introduced, time needs to be considered. Therefore, in truthiness tables, we create consider it as an input variable and therefore we now actually talk about predicted next value (instead of output), and the previous value (the input containing previous temporal data, which does not include the function's standard output).
They are represented as:
- `Q(t)` the previous one
- `Q(t + 1)` the next one

This circuit type, is actually critical for [[Memory|memory circuits]] to be functional.

The single issue with temporal circuits, is that inconsistencies can happen when couple with other both temporal and non-temporal circuits. To solve that, a core system called [[Clock|clock]] is used to establish when circuits will "react", preventing therefore miss-synchronization between them.