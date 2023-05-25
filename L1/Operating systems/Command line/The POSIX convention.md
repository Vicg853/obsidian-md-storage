The POSIX convention, determines how command line programs should be used and how they should be interpret such given input.

It has a pretty simple and straight-forward set of rules, along with some variations:
> [!abstract] Two child types
> _Arguments_ and _Options_

#### Options
These a simple characters that represent an option, that can be passed to the program. We stand them out, by placing a hyphen (``-``) before them: ``-o``. 

Originally, a single letter was allowed and mixing multiple letters together, would result in multiple chained options: ``-abc`` is the same as ``-a -b -c``. However nowadays, so called long options (in GNU systems for example) have been extending the convention and some command lines accept both types, even when using the same command: ``-abc -name``. Its purely for the program to decide it.
> [!info] 
> Sometimes long options, can have a double hyphen notation for separation: ``--long-opt``

> [!question] Curiosity about BSD like OSs
> On BSD OSs, options do not present hyphens before them

#### Arguments
These are values passed to the program in an either textual, numeral or other formats. Arguments must be either:
- written standalone, one after the other and after or at the end of the program's name: ``./my_prog "a"``;
- after an argument accepting option. When combined with them, the value must be passed just after the option, whilst accepting at least a single space in between them: ``-o "a"`` or ``-o"a"``