**Time Spent: 8 hours**

# Topics #

  * Complete Bipartite Graphs
  * Bipartite Graphs
  * Complete k-partite Graphs


# Details #

**1.** Building off of the observations made on Day 3 regarding the eigenvalues of complete bipartite graphs, I sought to prove that the formula I described applied to all complete bipartite graphs. To do this, I came up with the general form of the adjacency, Laplacian, and Normalized Laplacian matrices for complete bipartite graphs. Using this structure, I went through every eigenvalue that I observed and found a general eigenvector that would produce the desired eigenvalue for each matrix. Unfortunately, my background in linear algebra is such that, because I am not working with the characteristic polynomial, I cannot prove that other eigenvalues are not present (although none others were observed to be) and that the multiplicities of each eigenvalue must be what I described. I have only shown that eigenvalues that I observed to be present must be present.

3 hours

**2.** I continued examining bipartite graphs to try and find any extensions of what I had discovered for bipartite graphs. Unfortunately, I the only patterns I observed were ones that had already been given to me, that for the adjacency matrix of a bipartite graph, if λ is an eigenvalue, then -λ is also an eigenvalue, and that for the normalized Laplacian matrix, if λ is an eigenvalue, then 2-λ is also an eigenvalue. I was able to use linear algebra to explain the first theorem, but not the second. I may revisit this later, if time permits.

2 hours

**3.** I attempted to expand what I had described about complete bipartite graphs to complete k-partite graphs. I first looked at tripartite graphs to get a sense of how it would generalize, then make the following general conjecture.

For a complete k-partite graph K m1,m2,...,mk,

  * The eigenvalues of the adjacency matrix are 0 with a multiplicity of v-k, where v = the sum of m1, m2,...,mk is the number of vertices, k-1 negative eigenvalues, and 1 positive eigenvalue.
  * The eigenvalues of the Laplacian matrix are 0 with multiplicity 1, v with a multiplicity of k-1, and v-mi with multiplicity mi-1 for each mi.
  * The normalized laplacian matrix has an eigenvalue of 0 with multiplicity 1, an eigenvalue of 1 with multiplicity v-k, and k-1 positive eigenvalues greater than 1 that sum to k.

For the Laplacian matrix, I was able to find eigenvectors corresponding to every eigenvalue except for v.

3 hours