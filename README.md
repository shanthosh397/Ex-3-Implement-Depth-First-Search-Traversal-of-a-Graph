# Ex-3-Implement-Depth-First-Search-Traversal-of-a-Graph

**Name:** SHANTHOSH G

**Register Number:** 2305003008

### Aim:
To Implement Depth First Search Traversal of a Graph using Python 3.

### Theory:

Depth First Traversal (or DFS) for a graph is like Depth First Traversal of a tree. 

The only catch here is that, unlike trees, graphs may contain cycles (a node may be visited twice). 

Use a Boolean visited array to avoid processing a node more than once. 

A graph can have more than one DFS traversal. Depth-first search is an algorithm for traversing or searching trees or graph data structures. 

The algorithm starts at the root node (selecting some arbitrary node as the root node in the case of a graph) and explores as far as possible along each branch before backtracking. 

### Algorithm:

**Step 1:** Construct a Graph with Nodes and Edges

**Step 2:** Depth First Search Uses Stack and Recursion

**Step 3:** Insert a START node to the STACK

**Step 4:** Find its Successors Or neighbors and Check whether the node is visited or not

**Step 5:** If Not Visited, add it to the STACK. Else Call The Function Again Until No more nodes needs to be visited.


### Program:

```
from collections import defaultdict
def dfs(graph, start, visited, path):
    path.append(start)
    visited[start] = True
    for neighbour in graph[start]:
        if not visited[neighbour]:
            dfs(graph, neighbour, visited, path)
    return path

graph = defaultdict(list)
n, e = map(int, input("Enter number of nodes and edges (n e): ").split())
print("Enter edges (u v):")
for i in range(e):
    u, v = input().split()
    graph[u].append(v)
    graph[v].append(u)
print("Graph:", dict(graph))
start = 'A'
visited = defaultdict(bool)
path = []
traversed_path = dfs(graph, start, visited, path)
print("DFS Traversal Path:", traversed_path)
```

### Sample Input:

```
A B
A C
B D
B E
C E
D E
```

### Sample Output:

```
Graph: {'A': ['B', 'C'], 'B': ['A', 'D', 'E'], 'C': ['A', 'E'], 'D': ['B', 'E'], 'E': ['B', 'C', 'D']}

DFS Traversal Path: ['A', 'B', 'D', 'E', 'C']
```

### Input: 

<img width="649" height="173" alt="Screenshot 2025-09-08 225923" src="https://github.com/user-attachments/assets/31718c54-3b2b-4379-b8df-ac43499de2cf" />

### Output:

<img width="1041" height="137" alt="Screenshot 2025-09-08 225936" src="https://github.com/user-attachments/assets/c61485de-fea6-4388-bd84-f7fa2a3aee51" />


### Result:

Thus, Depth first search algorithm  is sucessfully implemented on a graph using python3.
