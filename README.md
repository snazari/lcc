# LCC: Big graph data dimensionality reduction
### Purpose
This algorithm performs dimensionality reduction on big graph data. The purpose of dimensionality reduction in such datasets is typically to prepare the graph data for more fine grade subgraph matching.
Typicall, subgraph matching algorithms have polynomial time complexity in the number of nodes in the archive graph. Therefore its advantageous to reduce the archive graph first using a dimensionality reduction apprach such as LCC. 
### Background
Every graph can be decomposed into the union of a spanning tree and the edges of the cycles that are not part of the spanning tree.
The LCC algorithm implements a dimensionality reduction algorithm based on features that can be extracted from the cycles of the graph vertices. 
During the subgraph matching step, a MST is constructed which captures the rest of the graph.

#### LCC inputs 
Q (query graph, a subgraph) and A (the archive graph, the graph that Q is contained in)

#### LCC output 
T: V(A) --> V(Q)

#### Explanation 
LCC accepts a query graph and an archive graph to search. It is assumed A>>Q i.e. the order of the archive graph is much larger than the order of the query graph. 
The algorithm returns a mapping of nodes from the archive graph to the query graph. These are candidate matches. In performing the matching, the lcc algorihtm reduces the dimensionality of the graph.
This algorithm has time complexity O(V(A)).