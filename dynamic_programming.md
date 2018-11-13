# Dynamic Programming

Method for solving a complex problem by breaking it down into a collection of simpler subproblems, solving each of those subproblems just once, and storing their solutions using a memory-based data structure (array, map,etc)
 
 1. Grid
 2. Recursion
 3. Memoization
 4. Bottom-up
 
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
