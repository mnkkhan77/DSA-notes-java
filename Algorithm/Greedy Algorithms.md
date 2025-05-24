picking locally optimal solution in the hope of finding the global optimal solution. Doesn't always work

> sometimes sorting works, sometimes priority works for finding the next optimal item

- when not work? coin change and 0/1 knapsack problems
- when work then? Fractional Knapsack, Dijkstra's algorithm, Kruskal's algorithm, Huffman coding and Prim's Algorithm

> Greedy do not reconsider previous choices, as they make decisions based on current information without looking ahead.

## How to Identify Greedy Problems:

>**Can we break the problem into smaller parts?** 
For example – In activity selection problem, once we have selected a activity then remaining subproblem is to choose those activities that start after the selected activity.

>**Will choosing the best option at each step lead to the best overall solution?**
For example – In Dijkstra’s shortest path algorithm, choosing the minimum-cost edge at each step guarantees the shortest path.

## Common ways to solve greedy

### - Sorting
1. Job Sequencing - prioritizing higher profit jobs
2. Activity Selection - picking the activity which ends earlier (non overlapping activities)
3. Disjoint intervals - same as point 2
4. Fractional Knapsack - sorting based on profit/weight ratio and picking the highest to lowest
5. Kruskal Algorithm - to find MST, we pick smallest weight by sorting edges based on smallest weights

### - Priority Queue
1. Dijkstra Algorithm - picking smallest distance from source node to find shortest path. we use min heap for the distance
2. Connect N ropes - always picking the lowest two ropes to make the bigger rope repeatedly 
3. Minimum number of jumps - always picking the highest/largest value