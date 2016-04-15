#Optional work plan guidelines and steps.

# Introduction #
This is a 10 day internship/project.

# Phase I - Preliminary Investigation and Study (3 days) #
  1. Study R. J. Trudeau's book _Introduction to Graph Theory_.
  1. Study some of the overview sections in the graph theory course: http://www-math.cudenver.edu/~wcherowi/courses/m4408/gtln.html
  1. Review highlites of material in MIT course Graph Theory I: http://ocw.mit.edu/NR/rdonlyres/Electrical-Engineering-and-Computer-Science/6-042JSpring-2005/FF95BA8F-6457-4592-B473-349A5C1CA277/0/l8_graphs1.pdf
  1. Review highlites of material in MIT course Graph Theory II: http://ocw.mit.edu/NR/rdonlyres/Electrical-Engineering-and-Computer-Science/6-042JSpring-2005/888E52CA-D401-4DDC-A378-5128EA7AC400/0/l9_graphs2.pdf
  1. Peruse Matgraph basic documentation: http://www.ams.jhu.edu/~ers/matgraph/matgraph.pdf
  1. Read and try examples using Matlab in Matgraph document: http://www.ams.jhu.edu/~ers/matgraph/by-example.pdf
  1. Study and execute examples file `test.m`. Understand examples. Try some individually.
  1. Review some matrix theory. Good matrix theory reference: http://en.wikipedia.org/wiki/Matrix_%28mathematics%29
  1. Review eigenvalues. See `graphtheorynotes.pdf` under wiki downloads: http://graph-computations.googlecode.com/files/graphtheorynotes.pdf. Good eigenvalue reference: http://en.wikipedia.org/wiki/Eigenvalues

# Phase II - Run numerical tests and investigate conjectures (5 days) #
**1)** Make sure you  have the latest version of the matlab program test.m. Copy it from
http://code.google.com/p/graph-computations/downloads/list to `...\GraphProject\Hunter_Workspace`

**2)** Analyze r-walks using the wheel, cube or other graph. Print out a picture of the graphs and trace out some r-walks for r=1, 2, 3. Convince yourself that the i,j element of A^r (A to the rth power of the adjacency matrix) is the  number of r-walks from i to j. Can you prove why this is true?

**3)** Analyze Platonic solids: Tetrahedron, Cube, Octahedron, Dodecahedron, Icosahedron. See `test.m` for example of matgraph commands to generate these. When using Euler's polyhedral formula, how do we count the faces when we transform from a 3D object to a planar graph? The formula works for a 3D platonic solid as well a the platonic solid which has been continuously transformed into a planar graph. See http://en.wikipedia.org/wiki/Platonic_solid. How many vertices, edges and faces does a bucky ball have? Try Euler's polyhedral formula.

**4)** Euler's polyhedral formula works for any planar graph and for simple polyhedra (this is a deep and profound theorem). Simple polyhedra do not have "holes". See http://plus.maths.org/issue43/features/kirk/index.html. Generate some planar graphs and see how the formula applies to them. How do we get a planar graph from a bucky ball? Can you generate or find a picture of a bucky ball as a planar graph?

**5)** A graph is called regular if every vertex has the same degree. Generate some regular graphs (e.g. complete(g,10), cube(g), octahedron(g), dodecahedron(g),icosahedron(g)). Find the eigenvalues of the adjacency matrix of g. Look at deg(g). How can you tell if we have a regular graph by looking at the eigenvalues of the adjacency matrix? Determine if the bucky ball is a regular graph? What about the grid graph: grid(g,4,5)?

**6)** For a complete graph every vertex is connected to every other vertex by an edge, and the eigenvalues of the adjacency are particularly simple. Create some complete graphs for different numbers of vertices n (e.g. complete(g,n)) and deduce what the eigenvalues are in general.

**7)** A bipartite graph (or bigraph) is a graph whose vertices can be divided into two disjoint sets U and V such that every edge connects a vertex in U to one in V; that is, U and V are independent sets. See http://en.wikipedia.org/wiki/Bipartite_graph
Try generating some bipartite graphs. Try `complete(g,3,5)` for example. What special properties do the eigenvalues of the normalized graph Laplacian have for a bipartite graph. Try a number of different examples using matlab to prove your statement. Then, try to expand what you have discovered to n-partite graphs (graphs where the vertices can be divided into n disjoint sets such that no edge connects a vertex in a set to another vertex in the same set). How does this relate to complete graphs, since Kn is just a special case of an n-partite graph.

**8)** The dual of a graph is formed by making each face of the original graph a vertex of the dual, then joining pairs of vertices of the dual if the faces they belong to in the original graph share an edge. Is there a relationship between these two graphs? Keep in mind that the dual of a graph depends on the embedding of the original graph. Are there connections between different duals of the same graph? A complicating factor is that many duals are not simple. You may also want to consider looking back at regularity (since the duals of regular graphs are "face-regular") or platonic solids, since the dual of a platonic solid is another platonic solid (or, in the case of the tetrahedron, the same one!).

**9)** A subgraph of a graph is one that can be obtained by deleting edges or vertices from the original graph. A minor of a graph is a graph that is obtained by contracting 0 or more edges on a subgraph of the original graph. How can we use adjacency matrices to express subgraphs or minors, or the operations used to obtain one? Can we draw any connections between a subgraph or a minor and the original graph? One of the most interesting problems in graph theory is that of planarity. Can we embed some graph in the plane such that there are no edge crossings? It is known that all non-planar graphs contain K5 or K3,3 as a minor. Is there any way to determine if a graph contains K5 or K3,3 as a minor? Are there any connections between subgraphs or minors of the same graph?

**10)** In a connected graph, you can get from any vertex to any other vertex by moving along edges. Not all graphs are connected. What can you discover about the eigenvalues of the graphs that are disconnected. Are they related to the eigenvalues of their component graphs?

**11)** The complement of a graph is obtained by taking the original graph, removing all edges, and placing new edges wherever there was not one before. Is there anything interesting about this?

**12)** A cycle graph Cn consists of a single cycle of length n, with n vertices and n edges. Is there anything interesting about these graphs?

# Phase III - Wrap up investigation and organize results (2 days) #
**1)** Organize results and data, including some pictures of various graphs.

**2)** Formulate conclusions explaining how and why your numerical data and study supports these conclusions.

# Prepare Report #
**1)** Provide outline of your project.

**2)** Explain at a high level what a mathematical graph is and how you can obtain various
associated matrices.

**3)** Provide simple examples of what you did so even non-mathematicians can understand your project.

**4)** Talk about the tools that you used (computers and software to do your project).

**5)** State your conclusions.

**6)** State whether this project was worthwhile as a learning experience and if you would recommend a similar project to other students at your school.