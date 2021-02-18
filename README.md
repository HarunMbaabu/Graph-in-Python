# Implementing a Graph in Python. 


A graph is a data structure that consists of vertices that are connected ​via edges. It can be implemented with an:


### 1. Adjacency list

For every vertex, its adjacent vertices are stored. In the case of a weighted graph, the edge weights are stored along with the vertices.​


### 2. Adjacency matrix

The row and column indices represent the vertices: matrix[i][j] = 1matrix[i][j]=1 means that there is an edge from vertices ii to jj, and matrix[i][j] = 0matrix[i][j]=0 denotes that there is no edge between ii and jj. 

For a weighted graph,the edge weight is usually written in place of 11. 


![Visual Representation of a graph](https://github.com/LuxTechAcademy/Graph-in-Python/blob/main/download.png "Title")


## Implementation

### 1. Using an adjacency list
The following code implements a graph using an adjacency list: add_vertex(v) adds new vertex v to the graph, and add_edge(v1, v2, e) adds an edge with weight e between vertices v1 and v2.

~~~python 
# Add a vertex to the dictionary
def add_vertex(v):
  global graph
  global vertices_no
  if v in graph:
    print("Vertex ", v, " already exists.")
  else:
    vertices_no = vertices_no + 1
    graph[v] = []

# Add an edge between vertex v1 and v2 with edge weight e
def add_edge(v1, v2, e):
  global graph
  # Check if vertex v1 is a valid vertex
  if v1 not in graph:
    print("Vertex ", v1, " does not exist.")
  # Check if vertex v2 is a valid vertex
  elif v2 not in graph:
    print("Vertex ", v2, " does not exist.")
  else:
    # Since this code is not restricted to a directed or 
    # an undirected graph, an edge between v1 v2 does not
    # imply that an edge exists between v2 and v1
    temp = [v2, e]
    graph[v1].append(temp)

# Print the graph
def print_graph():
  global graph
  for vertex in graph:
    for edges in graph[vertex]:
      print(vertex, " -> ", edges[0], " edge weight: ", edges[1])

# driver code
graph = {}
# stores the number of vertices in the graph
vertices_no = 0
add_vertex(1)
add_vertex(2)
add_vertex(3)
add_vertex(4)
# Add the edges between the vertices by specifying
# the from and to vertex along with the edge weights.
add_edge(1, 2, 1)
add_edge(1, 3, 1)
add_edge(2, 3, 3)
add_edge(3, 4, 4)
add_edge(4, 1, 5)
print_graph()
# Reminder: the second element of each list inside the dictionary
# denotes the edge weight.
print ("Internal representation: ", graph)
~~~
