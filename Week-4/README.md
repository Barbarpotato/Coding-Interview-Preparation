# Working With Algorithm

## Divide and Conquer
Divide and conquer is an algorithmic strategy commonly used to solve large problems by breaking them down into smaller, more manageable problems and then combining the solutions to the smaller problems to create a solution for the larger problem. This strategy is often used to optimize algorithm performance by reducing the number of operations required to solve a problem.

The process of divide and conquer can be explained as follows:

1. Break the problem down into several smaller, similar subproblems.
2. Solve each subproblem recursively.
3. Combine the solutions from each subproblem to form a solution to the larger original problem.

Examples of divide and conquer algorithms include the quicksort algorithm for sorting a list of values, the merge sort algorithm for sorting an array, and the binary search algorithm for finding an element in a sorted array.

## Recursion
Recursion is a programming technique used in algorithms where a function calls itself in order to solve a problem. In other words, it is a process in which a function solves a problem by breaking it down into smaller sub-problems of the same type, and then solves each of these sub-problems by calling itself recursively.

Recursion is based on the concept of induction, where a problem is solved by dividing it into smaller sub-problems until the base case is reached. The base case is the simplest version of the problem that can be solved directly without recursion.

Recursion is commonly used in algorithms for tasks such as traversing data structures like trees or graphs, searching for elements in an array, or sorting data. It can simplify the code and make it more elegant and concise, but it can also have performance and memory usage implications, especially for problems with large input sizes or deep recursion depth.

To implement a recursive call, there are three main requirements:

1. Base Case: There must be at least one base case that can be solved without recursion. This is the stopping condition that will prevent the function from calling itself indefinitely.

2. Recursive Step: There must be a recursive step where the function calls itself with a smaller version of the problem to solve. This is what makes the function recursive.

3. Progress Towards the Base Case: The recursive step must move the problem towards the base case. In other words, each recursive call must bring the problem closer to the base case, or the stopping condition.

By meeting these three requirements, a recursive function can solve complex problems by breaking them down into smaller, more manageable sub-problems. However, it's important to keep in mind that recursive algorithms can be less efficient than iterative solutions, and may cause issues like stack overflow if the depth of recursion is too large.

## Dynamic Programming
Dynamic programming is an extension of Divide & Conquer and Recursion approaches, which in addition involves keeping a record of results generated from running the sub problems each time they are newly run. In subsequent runs instead of re computing results a look up is queried for the last time the question was asked, as said, this approach is called `memorization`.

this is when the results of previous calculations are stored and used in place of rerunning the calculations when the compiler identifies that the computation has been run for a previous task. To exemplify this, consider the question posed in the video about binary numbers. How many combinations were possible with a binary lock of six digits? In a previous video it was shown that you can discover this through exponentiation or finding the power of a number. So the same lock with six digits would have 2 to the power of 6 or 64 combinations. So 2 to the power of 6 equals 2 times 2 times 2 times 2 times 2. Alternatively, you can divide these into two groups where you have calculated 2 times 2 times 2 and again 2 times 2 times 2. That will result in 8 times 8 and again give the same result. Applying a divide and conquer approach to computing this efficiently using memorization would reduce the computations by first calculating to the power of 3 and again 2 to the power of 3:

```
2x2x2x2x2x2 = 64
#Divide And Conquer Method
(2x2x2)x(2x2x2) = 64
```

By applying memorization, the first 2 to the power of 3 would be computed, then reused for the second bracket, reducing the overall computation required. So, what sorts of problems are good fits for a dynamic solution? The dynamic programming approach, is commonly applied to combination or optimization problems.

When computing dynamic programming solutions:
1. you must firstly determine the objective function. That is the description of what the optimum outcome is to be. 
2. Next you must break the problem into smaller steps.

## Greedy Algorithms
A greedy approach would instead look at the list of solutions and implement a local optimization. Usually, the current most rewarding option is chosen. To make this more clear, let's take an instance of a CPU that has a list of tasks to be completed. Applying the dynamic programming approach would entail selecting a subset of activities that could be completed within a given time and executing these tasks.

in our CPU example, a greedy approach would involve selecting first the shortest running program and then the next shortest program and so on. While this might not lead to a globally optimized solution, it will reduce any overhead in calculating the most efficient subset of items. 

![alt text](/Week-4/Images/Greedy.png)

To better understand how these two approaches would differ, let us consider the problem of the shortest path. The image shows a map with nine different nodes, A, B, C, D, E, F, G, H and S. Each node is connected to another node by a weighted path. This weight reflects the cost that would be incurred by selecting this path. Thus, in our CPU example, a greedy approach would involve selecting first the shortest running program and then the next shortest program and so on. While this might not lead to a globally optimized solution, it will reduce any overhead in calculating the most efficient subset of items. 

When we started from node E the greedy algorithm will choose the shortest one between all coneected node, which is D, and then the next route to another node link which is 5 and 3 to node G, and so on.

This is a trade off when choosing a greedy approach over a dynamic one. While the overhead for a greedy algorithm is low and coding a solution is quite straightforward, it will not always guarantee that the best option is returned.
