There are a couple of characteristics that are present and common to most programming languages:
- they all have a vocabulary, defined as a couple of keywords and symbols with a special meaning for the reader
- alphanumeric characters, used in such pattern defined by it
- syntactic defining how all elements should be organized and ordered
- semantic
- comments which are considered as characters that shouldn't be directly interpreted and processed by the language

These rules and the contraints (more about them next) allow us to precisely define a languages way of writing and even automatic validity check procedures.

#### Interpretation steps
Similarly they all usually share the same three following interpretation steps:
1) Lexical analysis, tasked with the content's tokenization
2) Syntactic analysis where a token three is created
3) Analysis of previous structures consistency with the languages grammar and rules

[[Screenshot 2023-10-21 at 2.46.24 PM.png|Example]]

#### Formal language contraints definition
There is a common formal way of defining languages contraints in language, which state the following set definitions: 
- $\Bbb X$ (alphabet): a finite symbol set of so called "letter"s
- $\Bbb u$ (word): a finite concatenation (defined just bellow) of letters
	- It's length is noted $|\Bbb u|$
	- The empty word $\epsilon$, with a length of $0 = |\epsilon|$
- Concatenation is defined as: $w = u\cdot v = u_1 \dots u_p \cdot v_1 \dots v_q$ where $|w| = |u| + |v| = p + q$
  E.g.: ``u = jeu``, ``v = di`` therefore ``w = jeudi``

#### Algebraic and formal language connection
Three core concepts worth remembering when studying formal languages are:
- half group: E set capable of following associativity rules
- monoid: a half group E set, followed by a neutral element (can be compared to the identity matrix in matrix algebra) $x\forall x \in E,\ x\cdot e = e \cdot x = x$
- group: monoid E set, where for each element a symmetrical corresponding element exists $x\forall x \in E, \exists y \in E,\ x \cdot y = y \cdot x = e$
- free monoid: 

#### Language
A language, is a set of rules that put order to an alphabet. It can simply be illustrated by an example: $L =\ \{\ u \in X^*\ |\ x_1 \not\in\{0, \dots 9\ \}\ \}$ (taken form the earlies Cs' programming languages, formal language definitions)