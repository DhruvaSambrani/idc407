# Centrality

## Degree Centrality

The degree of a node is used as centrality measure. It is simple but insightful

## Eigenvector Centrality

Degree centrality assumes all neighbors are equal, but this is not the case.
Centrality of a node must depend on the centrality of its neighbors.

$$x_i = \kappa^{-1} \sum_{\text{neighbors}} x_j$$

This can also be written as $x_i = \kappa^{-1} \sum_j A_{ij} x_j \implies \kappa x = A x$. Hence, $x$ is the Eigenvector of the network. But from Perron-Frobenius theorem, we know $\kappa$ is the largest Eigenvalue, and $x$ is the associated Eigenvector.

For directed networks, we can have different left and right Eigenvectors. The appropriate one can be chosen according to case at hand. The problem however, is when a particular node has 0 centrality, it extends 0 centrality to each of its neighbors. For acyclic graphs, this can lead to the whole graph being 0 centrality, or more mathematically, it gives scores only to strongly connected conponents of 2 or more nodes or their outcomponents.

## Katz Centrality

As before, 

$$x = \alpha Ax + I \implies x = (I - \alpha A)^{-1} I$$

with the added $I$, we can give every node a "free" centrality which prevents the whole graph from having 0 centrality.

By varying $\alpha$, we can vary the amount of "free" centrality. $x$ however diverges as $\det (\alpha^- I - A) = 0$. Hence, when $\alpha < 1/\kappa_1$, we get convergence

## PageRank

The issue with Katz centrality is that it gives each outgoing node the same amount of centraity even if there are many. The centrality sharing should be diluted by the total out degree of the neighbour. Hence, we can take 

$$x = \alpha AD^-x + \beta I$$

which has solution $x = (I - \alpha A D^-)^-1 1$


## Hubs and authorities

Both indegree(authorities) and outdegree(hubs) can be important for centrality. Hence, we can write 2 equations

$$\begin{aligned}
   x &= \alpha A y,\\
   y &=\beta A^T x
\end{aligned}$$

or, combining the two, 

$$\begin{aligned}
   \lambda x &= AA^T x,\\
   \lambda y &= A^TA y,\\
   \lambda &= (\alpha\beta)^-
\end{aligned}$$

Since both $AA^T$ and $A^TA$ have the same spectra, we just solve for one.

## Closeness Centrality

We can use the mean shortest distance from/to other nodes.

$$C_i = \frac{n}{\sum_j d_{ij}}$$

This fails for unconnected graphs, and often $C_i$ is found by averaging only over connected components.

We could also take the harmonic mean of the distances which solves the problem.

## Betweenness centrality

It is a measure of how many shortest paths pass through the node in question.

$$x_i = \sum_{st} \frac{n^i_{st}}{g_{st}}$$ 
