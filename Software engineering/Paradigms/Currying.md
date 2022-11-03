In computer science and mathematics, currying is the technique of creating a function that takes multiple arguments and pass them to multiple functions, each receiving an only argument.

It is vastly use functional programming, as it provides a way to manage how child functions will receive their arguments. The same occurs in theorical computer science, as it provides a way to simplify studies over function that receive multiple arguments, by dividing the problem into smaller functions. 

Similarly, we have uncurrying, which is a function, that accepts another function. This first function will yield a new function whose arguments are the passed function and its own arguments. It will then finally return the passed in function's result. 
Take this example: we have an ``f`` function, it accepts a ``g`` function. ``f`` will create ``f'`` which receives ``g`` and ``g``'s arguments. ``f'`` will run ``g`` and output it. ``f``s output will subsequently ``g``'s output.