When defining language it is essential to think about its grammar, which is supposed to define phrases that can be composed on top of it as well as its syntax.

This definition allows phrases to be built as well as for verifying a phrase's compliance with the language.

#### Grammar and automatas
Technically, automatas and a languages grammar are the same, but, they differ in a single key property: you cannot declare and detect relative combinations with an automata. 

In a nutshell, using an example, you can't define that an ``x`` entity, will appear twice as much as an ``y``entity in a phrase. But grammar definition, can help us define such rules in a language. 

#### Definition (algebraic definition)
A language's algebraic grammar is algebraically expressed as it follows: 
$$G =\ \lt V_T, V_N, S, P \gt$$

With the following terms being:
- $V_T$ -  The set of tokens composing a language, such as the commonly present ``for``s, ``while``s and etc
- $V_N$ - A set of elements, that create separation between specific tokens