# Ex.No:2
# Ex.Name:Given a  houses of a city consisting of N 2D coordinates {x, y} where each coordinate represents the location of each house, the task is to find the minimum cost to connect all the houses of the city.
## Date:
## Aim:
To find the minimum cost to connect all houses in a city given their 2D coordinates using Kruskal’s Algorithm (Minimum Spanning Tree) in C++.

## Algorithm:
STEP 1: Start the program.

STEP 2: Represent each house as a vertex and each possible connection between houses as an edge.

STEP 3: Calculate the weight of each edge as the Euclidean distance between two houses:
​
STEP 4: Store edges in an edge list as (weight, u, v). Use addEdge(x, y, w) to store edges.

STEP 5: Sort the edge list in ascending order of weights.

STEP 6: Initialize a Disjoint Set Union (DSU) / Union-Find structure to keep track of connected components.

STEP 7: Iterate through the sorted edges:

For each edge (w, u, v), check if u and v belong to different sets.

If yes, include the edge in MST and merge their sets.

Add the weight to the total cost.

STEP 8: Repeat until all houses are connected (N-1 edges selected).

STEP 9: Output the total minimum cost.

STEP 10: End the program.




## Program:
```

void addEdge(int x, int y, int w)
{
    edgelist.push_back({w, x, y});
}

```


## Output:
<img width="1016" height="629" alt="{7A325AB2-6FF7-4587-A8C2-B45D16833F7D}" src="https://github.com/user-attachments/assets/ec8dcd30-61bf-40fc-bdeb-9d2216983af5" />



## Result:
The program outputs the minimum cost to connect all houses.

