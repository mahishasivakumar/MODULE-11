# Ex.No:4

# Ex.Name:Writ a CPP function to find the bipartite of a graph which is given by user.

## Date:

## Aim:
To check whether a given undirected graph is bipartite or not using BFS and coloring in C++.

## Algorithm:
STEP 1: Start the program.

STEP 2: Represent the graph using an adjacency list (vector<int> adj[]).

STEP 3: Initialize a color array of size V with -1 to indicate uncolored vertices.

STEP 4: For each uncolored vertex, do the following:

Assign color 0 and push it into a BFS queue.

STEP 5: While the queue is not empty:

Pop a vertex v with its color c.

For all adjacent vertices j of v:

If j has the same color c, the graph is not bipartite, return false.

If j is uncolored, assign it the opposite color and push into the queue.

STEP 6: Repeat for all vertices.

STEP 7: If no conflicts are found, the graph is bipartite.

STEP 8: End the program.




## Program:
```
bool isBipartite(int V, vector<int> adj[])
{
    vector<int> col(V, -1);
 
    queue<pair<int, int> > q;
   
    for (int i = 0; i < V; i++)
    {
        if (col[i] == -1)
        {
            q.push({ i, 0 });
            col[i] = 0;
            while (!q.empty()) 
            {
                pair<int, int> p = q.front();
                q.pop();
            
                int v = p.first;
                int c = p.second;
                 
                for (int j : adj[v])
                {
                   
                    if (col[j] == c)
                        return 0;
                   
                    if (col[j] == -1)
                    {
                        col[j] = (c) ? 0 : 1;
                        q.push({ j, col[j] });
                    }
                }
            }
        }
    }
    return 1;
}
 
```


## Output:
<img width="787" height="778" alt="{6EC26EB9-739E-4D69-8ACD-360E02D11C65}" src="https://github.com/user-attachments/assets/461af0fb-9b03-445f-a4c4-485edbbbedb2" />




## Result:
The program outputs true if the graph is bipartite, otherwise false.

