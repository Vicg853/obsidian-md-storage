## Associativite
A computer can't actually process a triplet (or more) ``OR`` or ``AND`` expressions. It is limited to 2. To solve this, in multiplication (``AND``) operations and addition (``OR``) operations, the computer (or more precisely: usually the used language) gives parts of the equation, degrees of priority. 
```
- (a+b)+c = a+(b+c)
- 
```

## Simplifications
Some equations can be simplified, which will improve time that the computer takes to perform its calculations. Here are the cases (actually, at least some of them) at the lowest level, where they can be improved:

### Idempotence
When you have an element, added to itself (aka it passes through an ``OR`` expression)
``a+a=a``
``a*a=a``

### Involution de ``!``
``!!a = a``
### Commutativit'e
``a + b = b + a``
``a * b = b * a``
