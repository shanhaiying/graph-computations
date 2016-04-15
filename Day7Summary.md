**Time Spent: 7 hours**

# Topics #

  * Standard Deviation of Adjacency Matrix Eigenvalues
  * Edge Contractions
  * Planar and Non-Planar Graphs
  * Graph Complements

# Details #

**1.** I began by revisiting my conjecture from yesterday regarding the standard deviation of the eigenvalues of the adjacency matrix eigenvalues. Looking at the formula for standard deviation, I tried to determine why what I had conjectured might be true. The presence of the (v-1) in the denominator is easily accounted for, since the formula for standard deviation calls for dividing by one less than the number of values. Since there are v eigenvalues, we divide by v-1. This then suggests that the sum of the squares of the deviations adds up to 2e. Since the mean of the eigenvalues of the adjacency matrix is 0, this implies that the sum of the squares of the eigenvalues of the adjacency matrix add up to 2e. Looking at my data table, this seems to be true for all graphs. I do not know how to prove this, although proving that the sum of the squares of the eigenvalues of the adjacency matrix add up to 2e would prove my equation directly relating the standard deviation of the number of eigenvalues of the adjacency matrix to the number of vertices and edges.

1 hour

**2.** I investigated edge contractions and their effects on eigenvalues. I generated a graph to use as an example, and contracted each edge to generate all of the different minors up to isomorphism that could be obtained through one edge contraction. I could not establish any strict relationship between the eigenvalues of the parent graph and the graph obtained through one edge contraction, although some minors had eigenvalues similar to other minors, particularly for the Laplacian matrix. This did not occur for every minor, though, so I was unable to develop a satisfactory relationship. I did not see a relationship arise among the standard deviations of the eigenvalues, so I did not develop a good sense about what sort of relationship there is between a graph and the minor that is obtained when one edge is contracted.

2 hours

**3.** I then tried to approach the topic of planarity, since it is a common topic in graph theory. It is known that a graph is non-planar (it cannot be drawn without edge crossings) if and only if it contains K5 or K3,3 as a subgraph or minor. I began by examining K3,3 and K5 and comparing them to planar graphs to see if there was any noticeable difference between the two graphs. I was unable to find any relationship.
When looking at non-planar graphs, I noticed that, of the examples that I analyzed, the standard deviation of the Normalized Laplacian matrix seemed to always be less than that of K5. I don't know how to analyze it more critically, with more examples, so I think I will leave it at that and conjecture that, if a graph is non-planar, the standard deviation of the eigenvalues of its Normalized Laplacian matrix is less than or equal to the standard deviation of the eigenvalues of the Normalized Laplacian matrix of K5, which is .6325. Note that the conjecture does not apply in reverse (that is, if the standard deviation is less than .6325, it does not imply that the graph is non-planar). I have shown this with examples.

2 hours

**4.** I explored the notion of the graph complement. If G is a graph on n vertices, then G', the graph complement of G, is obtained by removing all edges in G, and placing new edges wherever there were no edges before. I began by studying this from the standpoint of the adjacency matrix. I found out that you could obtain the adjacency matrix of the graph complement by subtracting the original adjacency matrix and the identity matrix from a matrix of ones. I also discovered that each of the eigenvalues of the Laplacian matrix (except for the first 0) could be paired with an eigenvalue of the Laplacian matrix of the complement that add up to n, the number of vertices. In addition, we can also find out how many components a graph's complement will have by looking at how often n appears as an eigenvalue of the Laplacian matrix. If n appears as an eigenvalue with a multiplicity of k, then the graph complement has k+1 components.

2 hours