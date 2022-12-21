## Interpolation symbols
**⊂** Is a proper subset of

**∩** Intersection (AND)

**∪** Union (OR)

**⊃** Superset of: if all elements from a B interval, are a part of a A interval, then B is a superset of A

**∃** There exists

**∀** For all

**∈** is an element of

**◦** composition of functions: $f: x \to y, g: y \to z \iff g(f(x))$  

## Intervals
**ℝ** Real number: integers, decimals, fractions, anything.

#### Interval modifiers 
_**``*``**_ excludes 0 from the interval, e.x.: ``ℝ*`` all reals, excluding 0
_**``\{n}``**_  excluding ``n`` from the interval, e.x.: ``R\{1}`` all reals excluding 1

## Other
#### function representation
This ``f(x)`` is not a function, but actually a number. If we wan't to talk specifically about a function, we can write it down this way: ``x -> f(x)``, this actually consists of the function ``f`` which we will apply ``x`` to.

We can think of it similar to how we represent it in programming (lets take JS as an example): 
```ts
function f(x: number) { return x }

const y = f(x); 
//y, is an integer and not a function, the equal's right hand, consists of a number

const y_2 = () => f(x);
//as for this, here, y_2, is a function, the equal's right hand, consists of a function definition

y_2(); //We can even call it
```