The entire dataset, consisting of [[🕸️Nodes]], [[🕸️Relationships Edges]], [[🕸️Labels]], and [[🕸️Properties]], forms a graph. 
A graph is a collection of interconnected nodes and relationships that represent a specific domain or problem space.
It can be visualized as a network of nodes connected by edges.

[[Hop]]
[[Graph Databases]]


Lets say Tom Hank
The node labels are:
- `Person`
- `Actor`
- Labels shape the domain by grouping (classifying) nodes into sets where all nodes with a certain label belong to the same set.
The properties are:
- `name: Tom Hanks`
- `born: 1956`
The node can be created with Cypher using the query:
``` Cpher
CREATE (:Person:Actor {name: 'Tom Hanks', born: 1956})
```