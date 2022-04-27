### Intro
As explained on Wikipédia: "*In [computing](https://en.wikipedia.org/wiki/Computing "Computing"), **memoization** or **memoisation** is an [optimization](https://en.wikipedia.org/wiki/Optimization_(computer_science) "Optimization (computer science)") technique used primarily to speed up [computer programs](https://en.wikipedia.org/wiki/Computer_programs "Computer programs") by storing the results of expensive [function calls](https://en.wikipedia.org/wiki/Subroutine "Subroutine") and returning the cached result when the same inputs occur again.*".
	<sub><sup> Source: [Wikipédia](https://en.wikipedia.org/wiki/Memoization) </sup></sub>

This technique is used on computer science to optimize a program performance by storing already processed results from a function, preventing then repeated runs on an already found result. Example: 
> We create a simple ``1 + x`` addition function, without memoization on this function we would have to calculate every time the result for 1 + 2 when it is called. 
> 
> But with memoization we could simply store the result every time. Now when we ask for 1 + 2 multiple times, from the second time and on, we will have the result instantly. 
> ```javascript 
> //-------------- Not memoized 
> function add(x) {
> 	return 1 + x;
> }
> add(2) //Processes 1 + 2 and returns the result 
> add(2) //Processes 1 + 2 and returns the result 
> 
> //-------------- Memoized
> const results = [] //Following format {x: number, result: number}
> function addM(x) {
> 	const memo = results.indexOf(res => res.x === x);
> 	if(memo !=== -1) {
> 		return memo.res;
> 	}
> 	else {
> 		const calc = 1 + x;
> 		results.push({x, result: calc});
> 		return calc;
> 	}
> }
>
> addM(2) //Processes 1 + 2, stores the result and then returns it 
> addM(2) //Finds x = 2 result on the results var and returns it instantly
> ```

