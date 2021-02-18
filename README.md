# Implementing a Graph in Python. 


A graph is a data structure that consists of vertices that are connected ​via edges. It can be implemented with an:


### 1. Adjacency list

For every vertex, its adjacent vertices are stored. In the case of a weighted graph, the edge weights are stored along with the vertices.​


### 2. Adjacency matrix

The row and column indices represent the vertices: matrix[i][j] = 1matrix[i][j]=1 means that there is an edge from vertices ii to jj, and matrix[i][j] = 0matrix[i][j]=0 denotes that there is no edge between ii and jj. 

For a weighted graph,the edge weight is usually written in place of 11. 


![Visual Representation of a graph](relative/path/to/img.jpg?raw=true "Title")