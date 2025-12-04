# Ex.No:1  
# Ex.Name: Minimum Spanning Tree (MST) using Prim’s Algorithm  

## Date:  

## Aim:  
To write a C++ program to generate the **Minimum Spanning Tree (MST)** of a weighted, undirected, and connected graph using **Prim’s Algorithm**, and to find the sum of weights of the MST.  
<img width="347" height="319" alt="image" src="https://github.com/user-attachments/assets/c87f1b28-f4b7-4464-8d37-6d28652314e0" />

## Algorithm:  
1. Start the program.  
2. Input the number of vertices `V` and edges `E`.  
3. Store the graph as an adjacency list with edge weights.  
4. Initialize:  
   - A priority queue (min-heap) to pick the edge with the minimum weight.  
   - A visited array to mark selected vertices.  
   - `MST_cost = 0`.  
5. Start from vertex `0` (or any vertex).  
6. At each step, select the smallest edge that connects a visited vertex to an unvisited vertex.  
7. Mark the vertex as visited, add its edge weight to the `MST_cost`, and record the edge.  
8. Repeat until all vertices are included in the MST.  
9. Print the edges of the MST and the total cost.  
10. Stop the program.  

## Program:
```cpp
/*
#include<bits/stdc++.h>
using namespace std;
# define INF 0x3f3f3f3f

// iPair ==> Integer Pair
typedef pair<int, int> iPair;

// This class represents a directed graph using
// adjacency list representation
class Graph
{
	int V; // No. of vertices

	// In a weighted graph, we need to store vertex
	// and weight pair for every edge
	list< pair<int, int> > *adj;

public:
	Graph(int V); // Constructor

	// function to add an edge to graph
	void addEdge(int u, int v, int w);

	// Print MST using Prim's algorithm
	void primMST();
};

// Allocates memory for adjacency list
Graph::Graph(int V)
{
	this->V = V;
	adj = new list<iPair> [V];
} 
void Graph::addEdge(int u, int v, int w)
{
	adj[u].push_back(make_pair(v, w));
	adj[v].push_back(make_pair(u, w));
}

*/

int main()
{
	// create the graph given in above figure
	int V;
	int edges,vertices,u,v,w;
	//cout<<"Enter number of vertices and edges: ";
    cin>>vertices>>edges;
    V=vertices;
	Graph g(V);
    for(int i=0;i<edges;i++){
        cin>>u>>v>>w;
        g.addEdge(u,v,w);
    }
    cout<<"Prim's MST edges are:";
    g.primMST();
    // Write your code here
    
  
	return 0;
}
```

## Output:
<img width="861" height="867" alt="image" src="https://github.com/user-attachments/assets/d1387327-9998-471e-a36c-d06bdcb1e6c3" />

## Result:
```
Input:
3 3
0 1 5
0 2 1
1 2 3

Output:
Prim's MST edges are:
2 - 1
0 - 2
MST cost = 4
```
