There are two key elements, or actually a model, that founds all of computer programming technologies: expressions and operators. 

These two basic elements make most of a programming language's lexical scope and be connected one to another by expressions, leading into other expressions and so on.

### Expressions
An expression is the most simple token in a programming language. They're everywhere. Some examples are: ``3`` (an integer expression), ``3.14`` (a floating expression), ``'a'`` (a character expression), ``i`` (a variable expression), ``"bonjour"`` (a character table, or String, expression).

They all have one key characteristic: they contain a value.

These first ones are called _simples expressions_, tho we also have _complex expressions_: combinations of expressions and operators, that create new expressions. e.g.: ``3 + 3.14``, or ``4 * 'a'`` (this is right syntactically-wise, we're not considering its correctness logically-wise).

#### Characteristics
Every expression has each one of these characteristics:
- It holds a value or an address;
- It has a type;
- It may be able to have an onboard-effect: it may perform an operation, while still expressing a value, such as ``if(i = 3)`` in C++: this expression will affect 3 to ``i``, which is in itself an expression, expressing ``i`` new value, which means that ``3`` will be returned to ``if`` and we know that integers can be coerced into boolean values, where an integer different than ``0`` is always true.

### Operators
We have many operators, which when joined with expressions, allows us to create more complex expressions and therefore move forward.

Operators are abundant and each one has two key characteristic:
- a priority, that makes it be evaluated before other operators
- an interpretation direction, that changes de actual order that an expression combination is performed

![[original_6e031888-d803-4f88-b98e-f3d439503aef_IMG_20230215_111052111.jpg]]


### Others

#### LValue
The famous LValue ("left value") characterises an assignable expression. It does not necessarily mean anymore, that this expression is in the left-hand side of na operator, this is defined by the compiler. 
