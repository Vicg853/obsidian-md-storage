Real-life problems can be solved in many different ways, with the use of various algorithms. Among them, we have what the so called "linear programming" field. This field surrounds a core programming model, that makes use of linear algebraic properties and functions, to solve an availability to optimal quantity dilema (or more specifically: either a maximum value or a minimum value).

How so? Consider the case we need to produce x quantity of a given product and y of another one. Then add a new layer to it: we have limited u and v quantities of base elements, used by both products. 
Which is optimal climax configuration, allowing us to reach a peak production in each them?

> [!reminder]
> A linear algebraic function follows the following structure:
> 
> $\ \ \ f: x\mapsto cx$ 
> 
> Where $c$ is a constant coefficient
> It can hold many variable as well, in form of an addition.
> 
> $\ \ \ f: x_1 \dots x_n \mapsto c_nx_1 + \dots + c_nx_n$ 

## Algebraic modelization
The followed algebraic algorithm used on linear programming is summed up to a simple linear function called the objective (or economic function): of which we analyse the result, with the intent to achieve the maximum/minimum result. 

To solve it, we use a set of sub-equations, that can consists of both equalities or inequalities and are called constraints.

This translates to: 
$$
\begin{array}{l}
\max \mathrm{or} \min \Bbb Z = x_1c_1 + \dots + x_nc_n\\
\mathrm{for}\\ 
\ \ \ \ x_1a_{11} + \dots + x_na_{1n} \le \mathrm{or} \ge b_1 \\
\ \ \ \ \vdots \\
\ \ \ \ x_1a_{m1} + \dots + x_na_{mn} \le \mathrm{or} \ge b_m \\
\end{array}
$$

> [!info]
> $b_m$ corresponds to the constraints that are applied to certain cases
> $a_nm$s and $c_nm$s to the coefficients applied to the quantities that we intend to find (we can for example consider them as costs)

A shorter alternative, on larger and more complex problems, is to write it down in a [[Normal form|sum format]] (a.k.a. the normal form).

## Three modeling pillars
There are three pillars guiding us on how to solve a problem using the linear algorithm. They are found by answering these questions:
1) Which quantities can we work on?
2) What are we looking forward to optimize?
3) Which are the constraints?

When solving linear problems our goal is to always either maximize, or to minimize the result.
