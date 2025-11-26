# Ex.No:5

# Ex.Name:In order to reach a destination, a motorcyclist would like to avoid bridge(s). Ensure that he avoids such roads so that he can reach his destination on time by avoiding bridge. write a CPP function to identify bridge(s) in a map of city to help the motorist.

## Date:

## Aim:
To identify all bridges (critical edges) in a city map represented as a graph so that a motorcyclist can avoid them to ensure uninterrupted travel. A bridge is an edge whose removal increases the number of connected components in the graph.

## Algorithm:
STEP 1: Start the program.

STEP 2: Represent the city map as a graph using an adjacency list adj[].

STEP 3: Initialize arrays for each vertex:

visited[] → to track visited vertices

disc[] → discovery times of vertices

low[] → lowest discovery time reachable from the vertex

parent[] → parent of each vertex in DFS tree

STEP 4: For each unvisited vertex u, perform DFS traversal using bridgeUtil(u, ...).

STEP 5: In DFS for a vertex u:

Mark u as visited and initialize disc[u] and low[u].

For every adjacent vertex v:

If v is not visited:

Set parent[v] = u and recurse DFS on v.

Update low[u] = min(low[u], low[v]).

If low[v] > disc[u], then edge (u, v) is a bridge.

Else if v is already visited and v != parent[u], update low[u] = min(low[u], disc[v]).

STEP 6: Repeat DFS for all unvisited vertices to find all bridges.

STEP 7: Output all bridges.

STEP 8: End the program.




## Program:
```
void Graph::bridge()
{
	bool *visited = new bool[V];
	int *disc = new int[V];
	int *low = new int[V];
	int *parent = new int[V];
	
    for (int i = 0; i < V; i++)
	{
		parent[i] = NIL;
		visited[i] = false;
	}
	for (int i = 0; i < V; i++)
	{
	    if (visited[i] == false)
	    {
	        bridgeUtil(i, visited, disc, low, parent);
	    }
	}
}

```


## Output:
<img width="528" height="780" alt="{F0AB5679-993E-4524-8349-14F58FA38C74}" src="https://github.com/user-attachments/assets/09c8e11c-25e5-4026-aa6b-91b25f8a31af" />



## Result:
The program outputs all edges in the city map that are bridges, helping the motorcyclist to avoid them for uninterrupted travel.

