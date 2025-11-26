# Ex.No:1
# Ex.Name: Given a weighted, undirected and connected graph of V vertices and E edges. The task is to find the sum of weights of the edges of the Minimum Spanning Tree.
## Date:
## Aim:
To find the sum of weights of the edges in the Minimum Spanning Tree (MST) of a weighted, undirected, and connected graph using Prim’s algorithm in C++.

## Algorithm:
STEP 1: Start the program.

STEP 2: Represent the graph using an adjacency list:

Each vertex stores a list of pairs (neighbor, weight).

STEP 3: Define a Graph class with:

V → number of vertices

adj → adjacency list

addEdge(u, v, w) → to add edges

STEP 4: Initialize a min-priority queue to select edges with the smallest weight.

STEP 5: Start from any vertex (e.g., vertex 0), mark it as visited.

STEP 6: Push all edges from the current vertex to the priority queue.

STEP 7: While the priority queue is not empty:

Extract the edge with minimum weight.

If the destination vertex is unvisited, add its weight to the MST sum.

Mark the vertex as visited.

Push all edges from this vertex to the priority queue that lead to unvisited vertices.

STEP 8: Repeat until all vertices are visited.

STEP 9: The sum of all selected edge weights is the MST weight.

STEP 10: End the program.




## Program:
```
void Graph::addEdge(int u, int v, int w)
{
    adj[u].push_back(make_pair(v,w));
    adj[v].push_back(make_pair(u,w));
    
}
```



## Output:
<img width="832" height="556" alt="{F5245DB5-899C-42F2-8449-01CBD4E9F02A}" src="https://github.com/user-attachments/assets/6f07f811-8f56-4df6-a362-76c1e2749b64" />



## Result:
The program calculates the sum of weights of the MST for a connected, weighted, undirected graph.

