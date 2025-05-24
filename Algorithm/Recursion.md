recursion is just a **concept of calling the itself** (the same function/method) directly or indirectly.

So how do we **end this infinite calling?** we use a condition which is called as **base case** like in case of arrays when the length reaches the end the recursion should stop.

So why we need recursion cause certain problems can easily be solved using recursion like **Tower of Hanoi, Tree or graph traversals**

### Structure
1. Define base case - like when array position reaches arr.length()-1
2. Define recursive case - like what should be the smaller version of the big problem? calc(arr, position+1)
3. Ensuring the recursion ends
4. combine all the solutions

>Difference between Recursion and Iterative solution - Recursion uses extra stack space

### Applications of Recursion
- Tree and Graph traversals
- Sorting algorithm
- Divide and conquer algorithm 
- Backtracking algorithm 
- Memoization - caching results to further processing or avoid recomputing answers

