# Graphs

A graph is a data structire that consists of `vertices`, or `nodes`, connected by lines called `edges`. Graphs will cover these terms:

- `Vertex` - A vertex, also called a “node”, is a data object that can have zero or more adjacent vertices.
- `Edge` - An edge is a connection between two nodes. Edges are written as `Edges = {(a,c),(a,d),(b,c),(b,f),(c,e),(d,e),(e,f)}`
- `Neighbor` - The neighbors of a node are its adjacent nodes, i.e., are connected via an edge.
- `Degree` - The degree of a vertex is the number of edges connected to that vertex.

An `undirected graph` is a graph where the edge can come from each node and it counts for two edges.

A `directed graph` is where the edge is directed, meaning that there can possibly be a one-way for a node. If a node points to another node, the latter node is the neighbor of the first node. 

A `complete graph` is where each node points to all nodes and vice versa.

A `connected graph` is a graph that has nodes that have a least one edge. An example of a connected graph is a `tree` implementation.

A `disconnected graph` is where some vertices may not have vertices.

`Cyclic graphs` are when a node can be traversed through and end back at itself and `acyclic` if the graph doesn't have a cycle. 

We can represent graphhs through an adjacency matrix or list.

A weighted graph is when an edge has a value. It is very similar to vector math. The weights of a graph are denoted as an integer in a matrix ranging from 0 to infinity. 

The two ways we can traverse through a graph are breadth first and depth first.


Real World uses of Graphs:

- GPS and Mapping
- Driving Directions
- Social Networks
- Airline Traffic
- Netflix uses graphs for suggestions of products

## Graph Implementation

1. Create a class `Graph` 
2. Create `__init__` method with `self.adjacency_list = {}`
3. Create `add` method
4. Create `add_edge` method
5. Create `get_node` method
6. Create `size` method
7. Create `get_neighbor`
8. Create class `vertex` (or `Node`), with init that has valuu as an argument. self.value = value
9. Create Edge Class with __init__ and vertex and weight as the arguments. 

