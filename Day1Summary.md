**Time Spent: 7 hours**

# Topics Covered #

  * Quick overview of resources

  * Using matrices to represent graphs and basic operations on graphs

  * The property of eigenvalues of a graph itself vs. a labeling of that graph

  * The corresponding relevance to matrix manipulation and eigenvalues

  * Some basic properties of the platonic solids

# Details #

**1.** I quickly reviewed the resources that had been provided or recommended to me by Dr. Argentati. The material provided useful information about graph theory or linear algebra, but very little information about the application of graph theory to linear algebra. One source (http://ocw.mit.edu/NR/rdonlyres/Electrical-Engineering-and-Computer-Science/6-042JSpring-2005/FF95BA8F-6457-4592-B473-349A5C1CA277/0/l8_graphs1.pdf) provided some detail about calculating the number of r-walks from one vertex to another. I did not read the proof so that I could explore it myself at a later time.

Time Spent: 1 hour

**2.** I reviewed how graphs can be represented in matrix form and how basic operations such as adding or deleting a vertex or edge affects the adjacency matrix. Of particular interest to me was the effect of relabeling a graph, since this affects the adjacency matrix but not the inherent structure of the graph. I generated an sample graph and tested the effects of relabeling on the eigenvalues of the adjacency matrix, laplacian matrix, and normalized laplacian matrix and, using Wolfram Mathematica, found the eigenvalues to be identical between each matrix of the original and relabeled graphs. This supports the assumption that seemed to be present in some of the preparatory material that I had read, which suggested that the eigenvalues did not depend on how the graph is labeled.

I used this knowledge to conjecture about the effects of switching a pair of rows and the corresponding columns in a square matrix on the eigenvalues of that matrix. I noted that switching rows u and v of a square matrix, then columns u and v of the same matrix, effectively switches the labels of vertices u and v of the graph if this represents the adjacency (or another) matrix of this graph. Since in no case does this relabeling have any effect on the inherent structure on the graph, the eigenvalues should remain constant. This should apply to non-simple graphs (such as those with loops or multiple edges) and directed graphs. Thus, I conjecture that switching two rows and the corresponding columns of a square matrix with non-negative entries will have no effect on the eigenvalues of that matrix.

Since this deals primarily with linear algebra, where my background is weak, I will not try to prove this, but will see if Dr. Argentati can comment on my conjecture.

Time spent: 3 hours

**3.** Using MATLAB, I analyzed some of the properties of the platonic solids, noting the number of edges, vertices, and faces of each graph and the eigenvalues of the adjacency matrix, laplacian matrix, and normalized laplacian matrix. Here are some things I noticed.

  * The eigenvalues of the adjacency matrix sum to 0 for all the platonic solids.

  * Each of the platonic solids is regular, meaning that the degree of each vertex is the same. The eigenvalues of the normalized laplacian matrix can be obtained by dividing each eigenvalue of the laplacian matrix by the common vertex degree for each platonic solid. I think I can prove why this is the case by examining the definition of the laplacian and normalized laplacian matrices.

  * The eigenvalues of the normalized laplacian matrix sum to the number of vertices.

  * The eigenvalues of the laplacian matrix sum to twice the number of edges. This immediately follows from the above two observations, since each vertex is adjacent to the same number of edges, so if each vertex has degree n, then n\*v gives us the number of edge-ends, which is twice the number of edges.

  * There seems to be a connection between the eigenvalues of the adjacency matrix and the eigenvalues of the laplacian matrix. Every eigenvalue of the laplacian matrix can be obtained by subtracting one eigenvalue of the adjacency matrix from another. I will explore this further, since I think I can get into a little more detail here.

Time spent: 3 hours