**Time Spent: 7 hours**
# Topics #

  * Observations about the eigenvalues of graphs
  * Observations about the eigenvalues of regular graphs
  * Explanations of the above using linear algebra
  * Bipartite Complete Graphs


# Details #

**1.** I began by reviewing the data I have collected and compiled it into a file, now on the downloads page. I reviewed the data to try and make more general conclusions about the eigenvalues of all graphs in general, but found myself unable to. I did notice that for k-regular graphs, the largest eigenvalue of the adjacency matrix is equal to k.

1.5 hours

**2.** Dr. Argentati explained some concepts from linear algebra that had the power to explain some of the observations that I had made about the sums of the eigenvalues of the matrices of any graph. He explained the concept of the trace of a matrix, which is equal to the sum of the entries along the main diagonal as well as the sum of the eigenvalues of the matrix. Using definitions of the adjacency, Laplacian, and Normalized Laplacian matrices, it became clear why:

  * The sum of the eigenvalues of the adjacency matrix is 0.
  * The sum of the eigenvalues of the Laplacian matrix is the number of edge-end (twice the number of edges).
  * The sum of the eigenvalues of the Normalized Laplacian Matrix is the number of vertices.

1 hour

**3.** We then examined how linear algebra could explain the relationship between the eigenvalues of the matrices of regular graphs. Because of a theorem in linear algebra that states
`λ(cI - A) = c - λ(A)`
for c a constant, I the identity matrix, and A a matrix, and two theorems that, together, imply that the largest eigenvalue of the adjacency matrix is equal to k for a k-regular graph, we were able to explain the relationship stated in Day 2, part 2. We also drew a direct relationship between the eigenvalues of the adjacency and Normalized Laplacian matrices.

1 hour

**4.** I began my study of bipartite graphs by analyzing complete bipartite graphs. I observed the following:

For a complete bipartite graph Km,n, m<=n,
  * The eigenvalues of the adjacency matrix are -√(mn), √(mn), and 0 with a multiplicity of m+n-2.
  * The eigenvalues of the Laplacian matrix are 0, m with multiplicity n-1, n with multiplicity m-1, and m+n.
  * The eigenvalues of the Normalized Laplacian matrix are 0, 1 with multiplicity m+n-2, and 2.

I intend to continue my study of bipartite graphs by examining their structure and looking at non-complete bipartite graphs. Eventually, I hope to generalize this to n-partite graphs.

3.5 hours