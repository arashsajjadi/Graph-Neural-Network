I am trying to gather a summary of what I learned in this course from different sources and share it with you.

# Graph Terminology & Representation

## Basic definitions of graph

In one restricted but very common sense of the term, a graph is an ordered pair $G=(V,E)$ comprising: 

  - $V$ , a set of **vertices** (also called nodes or points);
  - $E\subseteq  \set{   \set{x,y \}|x,y \in V , x\neq y \}$ ,a set of **edges** (also called links or lines), which are unordered pairs of vertices (that is, an edge is associated with two distinct vertices).
  
  To avoid ambiguity, this type of object may be called precisely an **undirected simple graph**. 
  

![Undirected svg](https://user-images.githubusercontent.com/47760229/190175645-47339095-3134-4184-866c-d752cbc16b8e.png)

*A graph with three vertices and three edges.*

------

In one restricted but very common sense of the term, a **directed graph** is an ordered pair $G=(V,E)$ comprising:

  - $V$ , a set of **vertices** (also called nodes or points);
  - $E\subseteq  \set{   \set{x,y \}|(x,y) \in V^2 , x\neq y \}$ , a set of edges (also called directed edges, directed links, directed lines, arrows or arcs) which are ordered pairs of vertices (that is, an edge is associated with two distinct vertices).

![220px-Directed svg](https://user-images.githubusercontent.com/47760229/190177608-65c9c6e5-386d-4170-bcfe-5a233eb51fc5.png)

*A directed graph with three vertices and four directed edges (the double arrow represents an edge in each direction).*

----------
While most traditional graph approaches use nodes and edges to define all the graph data, recent papers, especially in the neural network, allow us to introduce additional information in the form of **features**. These features are the additional information that each node could carry on

We can display these graphs as $G=(V, E,u)$. while $V$ represents vertices(nodes), $E$ represents edges(adjacency , weight) $=(A,W)$ and $u$ represents feature vector. We can also define different types of nodes, these graphs are called heterogeneous graphs. 

![1_g4BORkfnT7nmsw_gH_eSfw](https://user-images.githubusercontent.com/47760229/190186702-6fce2834-c5bb-4324-bc24-63a12df8395a.png)

## Adjacency matrix

In graph theory and computer science, an adjacency matrix is a square matrix used to represent a finite graph. The elements of the matrix indicate whether pairs of vertices are adjacent or not in the graph.

In the special case of a finite simple graph, the adjacency matrix is a (0,1)-matrix with zeros on its diagonal. If the graph is undirected (i.e. all of its edges are bidirectional), the adjacency matrix is symmetric. The relationship between a graph and the eigenvalues and eigenvectors of its adjacency matrix is studied in spectral graph theory.

### Undirected graphs
The convention followed here (for undirected graphs) is that each edge adds 1 to the appropriate cell in the matrix, and each loop adds 2. This allows the degree of a vertex to be easily found by taking the sum of the values in either its respective row or column in the adjacency matrix.


|                                                  Labeled graph                                                  |                                                 Adjacency matrix                                                |
|:---------------------------------------------------------------------------------------------------------------:|:---------------------------------------------------------------------------------------------------------------:|
| ![image](https://user-images.githubusercontent.com/47760229/190188197-e1b9f0e5-7d7d-46f0-8c0c-c44921ca07b1.png) | ![image](https://user-images.githubusercontent.com/47760229/190188240-7598eabe-742c-4d59-8c47-71548988fd99.png) |
| ![image](https://user-images.githubusercontent.com/47760229/190188317-1ebfd2b1-1a63-4b27-88e2-f492269daeb1.png) | ![image](https://user-images.githubusercontent.com/47760229/190188348-8c9decc1-a12b-4056-a971-0553ab12c879.png) |


### Directed graphs
The adjacency matrix of a directed graph can be asymmetric. One can define the adjacency matrix of a directed graph either such that

  1. a non-zero element $A_{ij}$ indicates an edge from $i$ to $j$ or
  2. it indicates an edge from $j$ to $i$.

The former definition is commonly used in graph theory and social network analysis (e.g., sociology, political science, economics, psychology). The latter is more common in other applied sciences (e.g., dynamical systems, physics, network science) where A is sometimes used to describe linear dynamics on graphs.

Using the first definition, the in-degrees of a vertex can be computed by summing the entries of the corresponding column and the out-degree of vertex by summing the entries of the corresponding row. When using the second definition, the in-degree of a vertex is given by the corresponding row sum and the out-degree is given by the corresponding column sum.




|                                                  Labeled graph                                                  |                                                 Adjacency matrix                                                |
|:---------------------------------------------------------------------------------------------------------------:|:---------------------------------------------------------------------------------------------------------------:|
| ![image](https://user-images.githubusercontent.com/47760229/190190050-56eb261f-405a-4088-88da-1cf958a578d6.png) | ![image](https://user-images.githubusercontent.com/47760229/190190076-9011d4f1-3db4-4958-b560-ebc47314b91d.png) |
| Directed Cayley graph of $S_4$                                                                                  | Coordinates are 0–23. (As the graph is directed, the matrix is not necessarily symmetric.)                      |

**We can also use float values for the adjacency matrix, which shows how the connections between nodes are powerful**

## Degree of graph (D)


|                                                  Labeled graph                                                  |                                          Adjacency matrix & node labels                                         |
|:---------------------------------------------------------------------------------------------------------------:|:---------------------------------------------------------------------------------------------------------------:|
| ![image](https://user-images.githubusercontent.com/47760229/190229873-1c8003cd-879f-45d8-b14e-26431a133a38.png) | ![image](https://user-images.githubusercontent.com/47760229/190229926-ce68a54b-029f-4030-88bb-cbb457826b8e.png) |

The **Degree matrix(D)** is a *diagonal matrix* defining the number of connections per node

![image](https://user-images.githubusercontent.com/47760229/190230594-8d47a28f-cadf-4c9a-89d8-1e1356fa89b5.png)

Degree matrix

## Laplacian of graph

Laplacian matrix $L:= D-A$ where $D$ is the degree matrix and $A$ is the adjacency matrix of the graph.

|                                                  Labelled graph                                                 |                                                  Degree matrix                                                  |                                                 Adjacency matrix                                                |                                                 Laplacian matrix                                                |
|:---------------------------------------------------------------------------------------------------------------:|:---------------------------------------------------------------------------------------------------------------:|:---------------------------------------------------------------------------------------------------------------:|:---------------------------------------------------------------------------------------------------------------:|
| ![image](https://user-images.githubusercontent.com/47760229/190231354-9f5cf50c-39bd-47d7-8149-c72b8d4d5508.png) | ![image](https://user-images.githubusercontent.com/47760229/190231370-d45c7b47-9e16-440d-af32-69c85fe63f58.png) | ![image](https://user-images.githubusercontent.com/47760229/190231382-a39de8df-4c6c-44d2-bdb9-b4834da244fe.png) | ![image](https://user-images.githubusercontent.com/47760229/190231392-52add2f9-8e22-45ff-ace7-2da9ccd22df2.png) |

If our graph is weighted, the Laplacian is defined as $L:=D-W$ where $W$ is weighted matrix.

## Definition Of Graph Representation Learning

![image](https://user-images.githubusercontent.com/47760229/190233166-61e24ad1-144f-46e2-aaaf-7934279b7109.png)



