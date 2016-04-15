Time Spent: 8 hours

# Topics #

  * Edge Deletion
  * Vertex Deletion
  * Standard Deviation of the Eigenvalues of the Adjacency Matrix


# Details #

**1.** To begin my study of subgraphs and minors, I examined the effects of deleting a single edge from the graph. I tried this with numerous examples, and, for a given graph, deleted each edge to compare the subgraphs obtained by deleting a single edge with each other. I observed that

  * There does not appear to be any strict relationship between the eigenvalues of the original graph and the eigenvalues of the graph obtained by deleting one edge for any matrix.
  * The maximum eigenvalue of the adjacency matrix of the original graph is greater than (although it may turn out this is really greater than or equal to), the maximum eigenvalue of the adjacency matrix of the graph obtained by one edge deletion.
  * The maximum eigenvalue of the Laplacian matrix of the original graph is greater than or equal to the maximum eigenvalue of the Laplacian matrix of the graph obtained by one edge deletion.
  * The standard deviation of the eigenvalues of the Normalized Laplacian matrix of the original graph is less than the standard deviation of the eigenvalues of the Normalized Laplacian matrix of the graph obtained by one edge deletion. This also holds true if the 0 value is not considered.
  * The standard deviation of the eigenvalues of the adjacency matrix of the original graph is greater than the standard deviation of the eigenvalues of the adjacency matrix of the graph obtained by one edge deletion. Moreover, the standard deviations of the eigenvalues of the adjacency matrix of all graphs obtained by one edge deletion from the same parent graph are equal!

I have no idea how to go about proving this, so I probably won't.

3 hours

**2.** I then examined the effects of deleting a vertex from a graph, where when a vertex is deleted, all edges incident to that vertex are deleted as well. I tried this with numerous examples and, for a given graph, deleted each vertex to compare the subgraphs obtained by deleting a single vertex with each other. I observed that

  * There does not appear to be any strict relationship between the eigenvalues of the original graph and the eigenvalues obtained by deleting one edge for any matrix.
  * The minimum (or maximum) eigenvalue of the adjacency matrix of the original graph is less than or equal to (or greater than or equal to) the minimum (or maximum) eigenvalue of the adjacency matrix obtained by deleting a vertex.
  * The maximum value of the Laplacian matrix of the original graph is greater than or equal to that of the graph obtained by deleting a vertex.
  * Deleting a vertex increases the standard deviation of the eigenvalues of the Normalized Laplacian matrix. The higher the degree of the vertex deleted, the greater the change (If deleting a vertex of degree d produces a change of e, then deleting a vertex of degree greater than d produces a change greater than e).
  * The standard deviations of the eigenvalues of the adjacency matrix of all graphs obtained by deleting a vertex of the same degree d are equal.

3.5 hours

**3.** In the last two questions, I noticed that the standard deviation of the eigenvalues of the adjacency matrix (henceforth referred to as Sa) seemed to depend on how many edges were removed (in the first part, I removed only one edge, and in the second part, it depended on the degree of the vertex removed). I wondered if Sa only depended on how many edges were in the graph. Looking over the graphs I had used today, that was immediately proved untrue. I then conjectured that it depended on only the number of edges and vertices. To explore this, I constructed all possible simple graphs up to isomorphism consisting of 5 vertices and 7 edges, and it suggested that this was true. Looking back over all examples from today supported my conjecture. Finally, I tabulated my data and determined a formula to directly determine Sa from the number of vertices and edges, which I proudly present below.

Sa = √(2e/(v-1)), where v and e are the number of edges and vertices, respectively.

Note that this is just a conjecture based on existing data. I would not know how to prove this, and may continue to run examples to attempt to verify this.

1.5 hours