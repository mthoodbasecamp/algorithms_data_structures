# Graphs
Way to represent networks.

## Breadth-First Search
If there's a path from A to B.

## Dijkstra's algorithm
Shortest path to X for weighted graphs.

1. Graph
2. Parents
3. Cost
4. List/Array to keep track of nodes already processed.


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
