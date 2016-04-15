#matgraph examples


# Introduction #
This Wiki provide information and issues concerning Matgraph

# Some Useful Links #
matgraph toolbox webpage:
http://www.ams.jhu.edu/~ers/matgraph/

matgraph introductory guide:
http://www.ams.jhu.edu/~ers/matgraph/matgraph.pdf

matgraph tutorial and examples:
http://www.ams.jhu.edu/~ers/matgraph/by-example.pdf

matgraph commands:
http://www.mathworks.com/matlabcentral/fx_files/19218/1/content/matgraph/html/index.html


# Sample Test Program #
```
% test.m
% Sample commands to generate and manipulate graphs using MATLAB
% Rico Argentati 4/14/2010

%define some empty graphs
g=graph
h1=graph
h2=graph

% define a 5 x 5 grd graph
grid(g,5,5)

% get size, degrees of vertices or edges, basic size of graph
size(g)
deg(g)
edges(g)
display(g)

%draw graph with numbered vertices
ndraw(g)
% compute normalized graph laplacian
L=nlaplacian(g)
% get eigenvalues of normalized laplacian
a=eig(nlaplacian(g))
% get eigenvalues of normalized laplacian (shorter command)
a=eigl(g)
% compute adjacency matrix 
A=matrix(g)

% get graph from adjacency matrix
AA=[0 1 0 0
   1 0 0 0
   0 0 0 0
   0 0 0 0]
gg=graph
set_matrix(gg,AA)
ndraw2(gg)

% define other kinds of graphs
petersen(g)
random_planar(h1,5)
wheel(h2,8)
union(g,h1,h2)
bucky(g)
complete(g,3,5)
cube(g,4)
grid(g,4,5)
path(g,6)

% utility graph 
complete(g,3,3)
 
cycle(g,5)

% star graph - general complete(g,1,n)
complete(g,1,5)

% claw graph
complete(g,1,3)

% platonic solids
% Euler formula holds: v - e + f = 2
complete(g,4) % tetrahedron
cube(g)
octahedron(g)
dodecahedron(g)
icosahedron(g)

% draw wheel graph on a new graph
wheel(h2,8)
ndraw2(h2)
% get adjacency  matrix
A=matrix(h2)
% returns logical values in A so have to change to real numbers (double
% precision
A=double(A)
eig(A)

% look at 1, 2 and 3 walks
A1=A
A2=A^2
A3=A^3
```