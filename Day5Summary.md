**Time Spent: 8 hours**

# Topics #

  * Graph Duals
  * Disconnected Graphs
  * N-cubes
  * Grid graphs


# Details #

**1.** I explored the relationship between a graph G and its dual G', which is obtained by placing a vertex for G' in each face of G, and drawing edges between vertices of G' if the corresponding faces of G share an edge. I also had to work under the constraint of only being able to work with simple graphs, even though many graphs produce duals that are not simple. For the graphs I analyzed, I was only able to produce one dual under isomorphism for each graph. I thus conjectured that if the dual graph G' of a graph G is simple, then all other duals to G are isomorphic to G'. I noticed this after hoping that I might be able to observe a relationship between two different duals to the same graph.

I was unable to observe a relationship between algebraic properties of the dual of a graph and the graph itself, which is frustrating. It is not too surprising, however, since I was not able to determine a method of determining the dual of a graph using any of the matrices associated with the graph. The dual is produced from an embedding, which the matrices do not account for.

3 hours

**2.** I examined the relationship between disconnected graphs and their components. Some experimentation suggested that for the adjacency matrix, Laplacian matrix, and Normalized Laplacian matrix, the eigenvalues consisted of the eigenvalues of the component graphs, with multiplicities adding. This supports the theorem that was provided to me that, for the Laplacian matrix, if the eigenvalues are ordered and λk = 0 but λk+1 != 0, then the graph has i components. I was able to prove this by examining the structure of the matrices of disconnected graphs.

2 hours

**3.** I analyzed the graphs of successive n-cubes. Based off of my analysis of the 0-cube through the 4-cube, I conjecture that:
  * The eigenvalues of the adjacency matrix are given by 2i-n with a multiplicity of nCi, where i is an integer from 0 to n.
  * The eigenvalues of the Laplacian matrix are given by 2i with a multiplicity of nCi, where i is an integer from 0 to n.
  * The eigenvalues of the Normalized Laplacian matrix are given by 2i/n with a multiplicity of nCi, where i is an integer from 0 to n.
Here, xCy represents the choose function. Note that, since the n-cube is n-regular, each of these statements is equivalent. Due to the irregular structure of the matrices of n-cubes, and the rapidity with which they scale (the number of vertices of an n-cube is 2^n, so it grows exponentially), I will not try to prove this.

1 hour

**4.** I attempted to analyze grid graphs. Their eigenvalues seem to exhibit some sort of patterns, with most of the ones that I analyzed (up to 1x5, 2x5, and 3x4) seeming involve small square roots or rational numbers, particularly in the eigenvalues of the adjacency and Laplacian matrices. However, I haven't been able to develop a coherent conjecture. I intend to revisit this later.

1 hour

**5.** I began analysis of subgraphs and graph minors by examining the operations by which they are obtained and the effects on the matrices and eigenvalues. This preliminary analysis did not include any examples, but focused more on a general sense of the effects of these operations. I will continue my analysis of this tomorrow.

1 hour