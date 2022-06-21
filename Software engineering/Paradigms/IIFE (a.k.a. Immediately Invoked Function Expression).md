_**Own def.:**_ An IIFE is a function which is executed upon it’s own definition. It is also known as a design pattern called Self-Executing Anonymous Function. It has two major features: the variables inside the functions scope are not accessible outside of it which also prevents global scope pollution and invokes the function immediately.

_**Oficial/extended def.:**_ An **IIFE** (Immediately Invoked Function Expression) is a [JavaScript](https://developer.mozilla.org/en-US/docs/Glossary/JavaScript) [function](https://developer.mozilla.org/en-US/docs/Glossary/Function) that runs as soon as it is defined. The name IIFE is promoted by Ben Alman in [his blog](https://web.archive.org/web/20171201033208/http://benalman.com/news/2010/11/immediately-invoked-function-expression/#iife). It is a design pattern which is also known as a [Self-Executing Anonymous Function](https://developer.mozilla.org/en-US/docs/Glossary/Self-Executing_Anonymous_Function) and contains two major parts:

-   The first is the anonymous function with lexical scope enclosed within the `[Grouping Operator](<https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Grouping>)` `()`. This prevents accessing variables within the IIFE idiom as well as polluting the global scope.
-   The second part creates the immediately invoked function expression `()` through which the JavaScript engine will directly interpret the function.

_**Links: -**_ [](https://developer.mozilla.org/en-US/docs/Glossary/IIFE)[https://developer.mozilla.org/en-US/docs/Glossary/IIFE](https://developer.mozilla.org/en-US/docs/Glossary/IIFE)

-   [](https://developer.mozilla.org/en-US/docs/Glossary/Self-Executing_Anonymous_Function)[https://developer.mozilla.org/en-US/docs/Glossary/Self-Executing_Anonymous_Function](https://developer.mozilla.org/en-US/docs/Glossary/Self-Executing_Anonymous_Function)

_**Snippet**_
```ts
(function () { 
	statements 
})(); 
//The (...) are called grouping operators
```
