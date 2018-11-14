# Graphs
Way to represent networks.

## Breadth-First Search
If there's a path from A to B. 

## Dijkstra's Algorithm
Shortest path to X for weighted graphs.
Greedy Alorithm: Always looks for highest value first.

1. Graph - Hash representation of model
2. Parents - What path it takes to get to that node from parent chain.
3. Cost - How long it takes to get to that node from the start
4. List/Array - to keep track of nodes already processed.

Process

1. Find lowest cost node not in processed array
2. While we have Nodes to process
3. Collect node's neighbors via graph hash. 
4. Collect node's neighbor's cost via Costs hash. 
5. Compare node's neighbor's cost. 
6. Cheaper to go through current node? Yes
  1. Update neighbor's Cost hash w new cost
  2. Update neighgbor's Parent hash with current Node
5. Add current Node to processed list.


```

node = find_lowest_cost_node(costs)

# ToDo: when to use while not vs while obj is not None

while node is not None:
  cost = costs[node]
  neighbors = graph[node]
  
  for n in neightbors.keys();
    new_cost = cost + neighbors[n]
    if costs[n] > new_cost:
      costs[n] = new_cost
      parents[n] = node
  
  processed.append(node)
  node = find_lowest_cost_node(costs)
    
def find_lowest_cost_node(costs):
  lowest_cost = float("inf")
  lowest_cost_node = None
  
  for node in costs:
    cost = cost[node]
  
    if cost < lowest_cost and node not in processed:
      lowest_cost = cost
      lowest_cost_node = node
  
  return lowest_cost_node
```

## Graph
Hash table representation.

```
graph["start"] = {}
graph["start"]["a"] = 6
graph["start"]["b"] = 3

graph["a"]= {}
graph["a"]["fin"] = 4

graph["b"] = {}
graph["b"]["a"] = 5
graph["b"]["fin"]=5
```

|Node Start|Node End|Distance|
|---|---|---|
|start|a|6|
| |b|3|
|a|fin|4|
|b|a|5|
| |fin|5|

## Cost
How long it takes to get to that node from the start

```
infinity = float("inf")
costs ={}
costs["a"] = 6
costs["b"] = 3
costs["fin"] = infinity
```

|Node|Costs|
|---|---|
|a|6|
|b|3|
|fin|infinity|

## Parents
What path does it take to get from that node to the start?
Keep track of parent chain for least expensive path.


parents = {}
parents["a"] = "start"
parents["b"] = "start"
parents["fin"] = None

|Node|Parent|
|---|---|
|a|start|
|b|start|
|fin|None|
