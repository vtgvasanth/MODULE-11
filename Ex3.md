# Ex.No:3  
# Ex.Name: Dijkstra’s Shortest Path Algorithm  

## Date:  

## Aim:  
To write a C++ program to find the **shortest distance from source vertex (0 / A)** to all other vertices using **Dijkstra’s Algorithm**.  
<img width="669" height="392" alt="image" src="https://github.com/user-attachments/assets/7e378640-796b-45e3-89ab-a7e799e8282c" />

## Algorithm:  
1. Start the program.  
2. Input the number of vertices `V` and edges `E`.  
3. Store the graph as an adjacency list with edge weights.  
4. Initialize:  
   - A distance array `dist[]` with infinity.  
   - Set `dist[0] = 0` (source).  
   - A min-priority queue to extract the vertex with minimum distance.  
5. While the queue is not empty:  
   - Pick the vertex `u` with the smallest `dist[u]`.  
   - For every adjacent vertex `v` of `u`, check if:  
     ```
     dist[u] + weight(u, v) < dist[v]
     ```  
     If yes, update `dist[v]` and push it into the priority queue.  
6. Repeat until all vertices are processed.  
7. Print the shortest distance of each vertex from the source.  
8. Stop the program.  

## Program:
```cpp

printf("Vertex Distance from Source\n");
for(int i=0;i<V;i++){
    cout<<char(i+65)<<" "<<dist[i]<<"\n";
}
}
```

## Output:
<img width="426" height="666" alt="image" src="https://github.com/user-attachments/assets/95a979f5-001b-4918-b0e7-f7210c595e1f" />

## Result:
```
Input:
6 8
0 1 7
0 2 12
1 3 9
1 2 2
2 4 10
4 3 4
3 5 1
4 5 5

Output:
Vertex Distance from Source
A 0
B 7
C 9
D 16
E 19
F 17
```
