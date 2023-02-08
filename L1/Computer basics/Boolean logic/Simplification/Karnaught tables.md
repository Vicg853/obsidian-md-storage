
A method that can be used to simplify boolean functions, are Karnaught tables. It is structured in such way, that allows us to find multiple different formats of the same function and even, the most efficient one.

This table consists in placing all Boolean variables, in even groups at first column and row, in their different forms (actual and inverse forms, e.g.: $a$ and $\bar a$). 
Based on the first form found, we fill out the table with "1"s, with matching variable patterns found in the function. Other cels a filled with "0"s. 

#### Basic
By creating multiple of two  groups of "1"s and selecting variables present in all columns and lines of the group, we can form each of the function's sibling [[Basic boolean expressions#Formats| disjonctive]] pieces. Those can than be joined by ``OR`` operators, which will result in a simplified function version.

![[karnaught_map_eg.png]]

We can visually see that the Karnaugh method, allowed us to considerably simplify our function.

#### Advanced
Even though the basic version allows us to already perform many simplifications, we can find even simpler functions. For that we, make an analysis of the original function and fill the table with indifferent variables (cels, which's value does not implicitly change the function's result).



