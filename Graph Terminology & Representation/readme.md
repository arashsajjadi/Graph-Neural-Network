I am trying to gather a summary of what I learned in this course from different sources and share it with you.

# Graph Terminology & Representation

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
