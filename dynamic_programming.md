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
 Pretend items below aren't available yet

 
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
