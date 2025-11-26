# Ex.No:3
# Ex.Name:You are a hiker preparing for an upcoming hike. You are given the height of the peaks with the efforts needed. You are situated in the top-left,  and you hope to travel to the bottom-right of the hill. You can move up, down, left, or right, and you wish to find a route that requires the minimum effort to reach all the peaks.
Write a C++ main() function to return the minimum efforts to reach all the peaks from the place where you start your hiking.
## Date:
## Aim:
To find a path from the top-left to the bottom-right of a grid of peaks such that the maximum effort between consecutive peaks is minimized. The effort between two adjacent peaks is the absolute difference in heights.

## Algorithm:
STEP 1: Start the program.

STEP 2: Represent the grid as a graph, where each cell is a vertex.

STEP 3: Define adjacency lists for each vertex:

Use addEdge(u, v, w) to connect adjacent vertices with edge weight w = abs(height[u] - height[v]).

STEP 4: Initialize a priority queue (min-heap) to store {current_effort, vertex}.

STEP 5: Initialize a distance array to track the minimum maximum effort to reach each vertex.

STEP 6: Start from the top-left vertex (0,0), set its effort to 0 and push into the priority queue.

STEP 7: While the queue is not empty:

Pop the vertex with the smallest effort.

For all adjacent vertices, calculate effort = max(current_effort, weight_to_neighbor).

If effort is smaller than previously recorded, update and push neighbor into the queue.

STEP 8: Repeat until the bottom-right vertex (rows-1, cols-1) is reached.

STEP 9: The value in distance[bottom-right] gives the minimum effort path.

STEP 10: End the program.




## Program:
```

void Graph::addEdge(int u, int v, int w)
{
	adj[u].push_back(make_pair(v, w));
	adj[v].push_back(make_pair(u, w));
}

```


## Output:
<img width="868" height="600" alt="{B5BBAD7E-CA10-4195-9899-AAD481B24267}" src="https://github.com/user-attachments/assets/53579dac-1f54-48fa-894d-823d4366642a" />



## Result:
The program outputs the minimum effort required to travel from the top-left to the bottom-right of the grid.

