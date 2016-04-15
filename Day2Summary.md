**Time: 8 hours**

# Topics Covered #

  * Matrix Manipulation
  * Observations about Regular Graphs
  * Complete Graphs
  * Generalizing observations about regular graphs to all graphs
  * R-walks and the Adjacency Matrix


# Details #

**1.** Dr. Argentati informed me that my hypothesis regarding matrix permutation was correct (see Day 1 Summary, pt 2). More generally, any permutation of the rows and the same permutation of columns preserves the eigenvalues. He also explained how this could be achieved through a permutation matrix and its transpose. I experimented with how this is achieved.

1 hour

**2.** I reexamined some of the discoveries I made about the Platonic solids. I explained the connection between the eigenvalues of the Laplacian matrix and the eigenvalues of the normalized Laplacian matrix. I also noted that this is not restricted to the Platonic solids, but applies more generally to all regular graphs. Some sampling of other regular graphs suggests that all of the other observations I made yesterday (Day 1 Summary, pt. 3) hold for regular graphs in general, not just the platonic solids. I was also able to make slightly more clearer my last observation. For a regular graph, I found that the eigenvalues of the Laplacian matrix can be obtained by subtracting each of the eigenvalues of the adjacency matrix from the largest eigenvalues of the adjacency matrix.

3 hours

**3.** I investigated complete graphs, and noticed that the eigenvalues of the adjacency matrix have 1 value equal to n-1 (where we deal with Kn), and n-1 values equal to -1. I was able to explore this through the definition of eigenvalues and eigenvectors, and found eigenvectors that are associated with both eigenvalues. I do not think that I can prove that there are not other eigenvalues without dealing with the characteristic polynomial, but I think that, given my experience with linear algebra, that that is beyond the scope of this project.

1 hour

**4.** I tried to generalize some of my observations about the eigenvalues of the different matrices of regular graphs to those of any graphs. I found that only the following three observations held.

  * The sum of the eigenvalues of the adjacency matrix is 0.
  * The sum of the eigenvalues of the Laplacian matrix is the number of edge-ends (or twice the number of edges)
  * The sum of the eigenvalues of the Normalized Laplacian matrix is the number of vertices.

I was not able to establish a relationship between the eigenvalues of any matrix with the eigenvalues of any other, as I had been able to do for regular graphs. I hope that I get an opportunity to revisit this, but I think it will be difficult to find a connection.

1 hour

**5.** I examined the theorem that states that if A is the adjacency matrix of a graph, then A^r gives the number r-walks from one vertex to another. I used the principles of matrix multiplication to attempt to explain this.

2 hours