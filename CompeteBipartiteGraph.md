Eigenvalues of adjacency matrix for complete bipartite graph

# Introduction #
If we have a complete bipartite graph say `complete(g,n,m)`
then the eigenvalues of the adjacency matrix are `+-sqrt(n*m)` and
`n+m-2` zeroes.

An outline of a proof is given below.


# Details #
It is hard to use the characteristic polynomial to prove this. The easier approach is to look at the structure of the adjacency matrix A, although it is still not that easy and uses some relatively advanced linear algebra concepts. We label the vertices so the first n are in the first set and the second m are in the second set with edges between these sets.

We obtain an adjacency matrix with 4 blocks: an n x n block of zeros and an n x m block of ones on top and an m x n block of ones and m x m block of zeros below.

A is an n+m x n+m matrix.

Now there are two independent column vectors in A which means that it has rank 2. This implies that there are n+m-2 zero eigenvalues and 2 nonzero eigenvalues. Our task then is to find the two nonzero eigenvalues.

We will construct two eigenvectors that will work. Let

```
x= [n ones  and  m values = sqrt(n/m)]=[1...1 sqrt(n/m)...sqrt(n/m)]
y= [n ones  and  m values = -sqrt(n/m)]=[1...1 -sqrt(n/m)...-sqrt(n/m)]
```

These eigenvectors were obtained through guessing and intuition!

Now it is not hard to show that A\*x= sqrt(nm) x and A\*y=-sqrt(nm) y. Since x and y are independent vectors that work for the eigenvalues +-sqrt(n/m) we are done and we know that the rest of the eigenvalues are zero because the rank(A)=2.

We should be able to extend these results using a similar approach to obtain eigenvalues for the graph Laplacian and normalized graph Laplacian.

We can now compute the eigenvalues of the the normalized Laplacian. For this case
NL = I - sqrt(1/(mn))A where A is the adjacency matrix. This is just a scaled
and shifted adjacency matrix, so the eigenvalues of NL are 1  minus the eigenvalues of A divided by sqrt(mn). So we get one 0, m+n-1 1s and one 2. Note that if we subtract them all from 2, we get the same set of values. This result was a theorem in the graph theory notes for bipartite graphs.

Calculating the eigenvalues of the Laplacian is harder and I don't have a proof for that case yet.


# Matlab Program to Test This Result or "Proof by Matlab" #
```
% test2.m
% test proof concerning complete bipartite graphs
n=3;
m=7;
complete(g,n,m);    % generate complete bipartite graph with set of n
                    % vertices and m vertices

A=double(matrix(g)); % get incidence matrix

% theoretical non-zero eigenvalues
c1=sqrt(n*m);
c2=-sqrt(n*m);

% generate eigenvectors
a=sqrt(n/m);
x1=[ones(n,1)' a*ones(m,1)']';
x2=[ones(n,1)' -a*ones(m,1)']';
    
% if A*x1=c1*x1 should get zero here
norm(A*x1-c1*x1)
A*x1-c1*x1

% if A*x2=c2*x2 should get zero here
norm(A*x2-c2*x2)
A*x2-c2*x2

% check computed eigenvalues
c1
c2
eig(A)
```