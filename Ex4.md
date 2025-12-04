# Ex.No:4  
# Ex.Name: Check whether a Graph is Bipartite  

## Date:  

## Aim:  
To write a C++ function to check whether a given graph is **Bipartite** or not.  
<img width="623" height="436" alt="image" src="https://github.com/user-attachments/assets/134b334c-b8ce-42dd-93f6-a0e057190f7d" />

## Algorithm:  
1. Start the program.  
2. Input the number of vertices `V` and edges `E`.  
3. Represent the graph using an adjacency list.  
4. Maintain a color array `color[V]`, initialized with `-1` (uncolored).  
5. For every unvisited vertex, perform BFS:  
   - Assign the starting node a color (say 0).  
   - Traverse its neighbors:  
     - If a neighbor is uncolored, assign it the opposite color and continue BFS.  
     - If a neighbor has the same color as the current node → **Not Bipartite**.  
6. If all vertices are properly colored without conflicts → **Bipartite**.  
7. Print whether the graph is Bipartite or not.  
8. Stop the program.  

## Program:
```cpp
/*
#include <bits/stdc++.h>
using namespace std;
class Graph{
    int numVertices;
    list<int> *adjLists;
    
  public:
    Graph(int V);
    void addEdge(int src, int dest);
};
// Add edge
void addEdge(vector<int> adj[], int s, int d) {
  adj[s].push_back(d);
  adj[d].push_back(s);
}

// Print the graph
void printGraph(vector<int> adj[], int V) {
  for (int d = 0; d < V; ++d) {
    cout << "\n Vertex "
       << d << ":";
    for (auto x : adj[d])
      cout << "-> " << x;
    printf("\n");
  }
}
vector<vector<int> > convert(vector<int> adj[],
                             int V)
{
    // Initialize a matrix
    vector<vector<int> > matrix(V,
                                vector<int>(V, 0));
 
    for (int i = 0; i < V; i++) {
        for (auto j : adj[i])
            matrix[i][j] = 1;
    }
    return matrix;
}
 
// Function to display adjacency matrix
void printMatrix(vector<vector<int> > adj, int V)
{
    for (int i = 0; i < V; i++) {
        for (int j = 0; j < V; j++) {
            cout << adj[i][j] << "   ";
        }
        cout << endl;
    }
    cout << endl;
}
 

int main() {
  int V;
  
   int i,e,u,v;
   cin>>V;
  // Create a graph
  vector<int> adj[V];
  
  cin>>e;
for(i=1;i<=e;i++)
  {
    cin>>u>>v;
    addEdge(adj,u,v);
  }

  // Add edges
  
  ////printGraph(adj, V);
  //cout << "Adjacency List: \n";
 // vector<vector<int> > adjMatrix
  //      = convert(adj, V);
 
    // Display adjacency matrix
   // cout << "Adjacency Matrix: \n";
   // printMatrix(adjMatrix, V);
   bool ans = isBipartite(V, adj);
    //returns 1 if bipartite graph is possible
      if (ans)
        cout << "Yes bipartite graph\n";
    //returns 0 if bipartite graph is not possible
      else
        cout << "No not a bipartite graph\n";
 
}*/
bool isBipartite(int V, vector<int> adj[])
{
    // vector to store colour of vertex
    // assigning all to -1 i.e. uncoloured
    // colours are either 0 or 1
      // for understanding take 0 as red and 1 as blue
    vector<int> col(V, -1);
 
    // queue for BFS storing {vertex , colour}
    queue<pair<int, int> > q;
   
      //loop incase graph is not connected
    for (int i = 0; i < V; i++) {
       
      //if not coloured
        if (col[i] == -1) {
           
          //colouring with 0 i.e. red
            q.push({i,0});
            col[i]=0;
            while(!q.empty())
            {
                pair<int,int>p = q.front();
                q.pop();
            

            
            
            
            
                  //current vertex
                int v = p.first;
                  //colour of current vertex
                int c = p.second;
                 
                  //traversing vertexes connected to current vertex
                for (int j : adj[v]) {
                   
                      //if already coloured with parent vertex color
                      //then bipartite graph is not possible
                    if (col[j] == c)
                        return 0;
                   
                      //if uncoloured
                    if (col[j] == -1) {
                      //colouring with opposite color to that of parent
                        col[j] = (c) ? 0 : 1;
                        q.push({ j, col[j] });
                    }
                }
            }
        }
    }
    //if all vertexes are coloured such that
      //no two connected vertex have same colours
    return 1;
}
```

 ## Output:
<img width="526" height="803" alt="image" src="https://github.com/user-attachments/assets/8391552a-276a-4430-98c6-1d0b0698e7c5" />

## Result:
```
Input:
4 4
1 3
0 2
1 3
0 2

Output:
Yes bipartite graph


Input:
9 9
0 1
1 2
1 7
2 3
3 5
4 6
4 8
7 8
1 3

Output:
No not a bipartite graph
```

