# Dynamic Programming

Method for solving a complex problem by breaking it down into a collection of simpler subproblems, solving each of those subproblems just once, and storing their solutions using a memory-based data structure (array, map,etc).
Keeps progressivly building estimates.


## When to use

1. Constraint - When trying to optimize something given a contraint. Knapsack = value of goods constrained by knapsack size.
2. Discrete subproblems - Dynamic programming only works when each subproblem is discrete - when it doesn't depend on other subproblems.

## Technique
 
 1. Grid
  1. What are values of cells?
   1. Goal: Maximize value. 
   2. Content: What you're trying to optimize.
  2. How do we divide into subroutines?
   1. Thre's no easy way to calculate formula. You have to experiment and find something that works.
Sometimes, algorithms aren't an exact recipe. They're a framework tahat you build your idea on top of.
   2. Helps set axes
  3. What are the axes of grid? From #2
  4. Account for granularily (0.5 vs 1)
 2. Recursion
 3. Memoization
 4. Bottom-up
 
 ## Questions
 
 1. Can I add more items? 
 Yes, Dynamic Programming keeps progressivly building estimates.
 2. Can value of estimates go down as we move down? 
 No, we are building current max estimate. Can't get worse than it was before.
 3. Can we change order?
 Yes, order doesn't matter.
 4. Can I add smaller items?
 Yes, but must change interval.
 5. Can I take fraction of item?
 No, not in dynamic programming. Either take an item or not.
 Solve by using Greedy Algorithm and take by highest value item first.
 5. Can rows/subproblems be dependents on each other?
 No, nly works when each subproblem is discrete.
 
 # Knapsack
 
 I have a knapsack that can carry 4lbs.
 Subproblems = solving for smaller knapsacks then bigger.
 At each cell: Do you take the item or not?
 At every row:
  Estimate is incrementally updated.
  Take item at that row or rows above it.
  Items below aren't available yet
 

 
 * Guitar: 1lb / $1500
 * Stereo: 4lbs / $3000
 * Laptop: 3lbs / $2000
 

|item\lbs|1|2|3|4|
|---|---|---|---|---|
|Guitar|
|Stereo|
|Laptop|



|item\lbs|1|2|3|4|
|---|---|---|---|---|
|Guitar| G : $1500 |G : $1500 | G : $1500 | G : $1500 |
|Stereo|
|Laptop|

Stereo is too heavy for 1, 2 and 3lb; So we take guitar.
At 4lbs, we choose guitar w/ most value.

|item\lbs|1|2|3|4|
|---|---|---|---|---|
|Guitar| G : $1500 |G : $1500 | G : $1500 | G : $1500 |
|Stereo| G : $1500 |G : $1500 | G : $1500 | S : $3000 |
|Laptop|

Estimate is incrmentally updated.
We assign a value to the space left over.

cell[i][j] = max of {
1. Previous Mac 
 cell[i][j] = (cell[i-1][j])
2. Value of current item + value of space 
 cell[i][j] = (Items Value) + (cell[i-1][j - items weight])

|item\lbs|1|2|3|4|
|---|---|---|---|---|
|Guitar| G : $1500 |G : $1500 | G : $1500 | G : $1500 | <- Old Estimate
|Stereo| G : $1500 |G : $1500 | G : $1500 | S : $3000 | <- New Estimate
|Laptop| G : $1500 |G : $1500 | L : $2000 | L + G : 32500 | <- Final Estimate

# Longest common substring

Search Engine Input: "HISH"
Suggest "FISH" or "VISTA"?

1. What am I trying to optimize? 
Which is a closer match -
Length of substring two values have in commong.

2. Subroutines?
Compare substrings. Each cell will contain length of longest substring.
Therefore, Axes will probably be two substrings.

3. Axes
The original vs the suggested

| | H | I | S | H |
|---|---|---|---|---|
| F |
| I |
| S |
| H |

If Substring includes previous letter

| | H | I | S | H |
|---|---|---|---|---|
| F | 0 | 0 | 0 | 0 |
| I | 0 | 1 | 0 | 0 |
| S | 0 | 1 | 2 | 0 |
| H | 0 | 1 | 2 | 3 |

