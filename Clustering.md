# Clustering

## Cliques

A fully connected subgraph is called a clique. It signifies a highly cohesive subgroup.

## Cores

Cliques are rare, so we define $k$-Cores which is a subgraph where each node has atleast $k$ neighbors.

All $l>m$ cores exist in $m$ core.

## k-components

Extending [[Quantitative Properties of Graphs#Components]], we can define $k$-components which is a subgraph with atleast $k$ [[Quantitative Properties of Graphs#Independant Paths, Connectivity and Cut sets\|Independant Paths]] between any 2 nodes

Again, $l>m$ component is contained in $m$ component. $k=1$ is the previous definition of component.

## Transitivity and Clustering Coefficient

Transitivity of a graph is defined as the case when $i\to j & j\to k \implies i\to k$.

We can define the Clustering Coefficient to be the fraction of paths of length 2 that are closed.

Alternatively, 

$$C = \frac{\text{# triangles}\*6}{# paths of length 2}$$

or

$$C = \frac{\text{# triangles}\*3}{# connected triples}$$


## Local Clustering

$C_i = \frac{\text{number of pairs of neighbors of i that are connected}}{\text{number of pairs of neighbors of i}}$

This tells us how much flow can be controlled between neighbors, but small values imply larger control.

## Redundancy

It is the average number of connections between neighbors of i.

$$C_i = \frac{R_i}{k_i-1}$$

[//begin]: # "Autogenerated link references for markdown compatibility"
[Quantitative Properties of Graphs#Components]: Quantitative Properties of Graphs#components "Quantitative Properties of Graphs#Components"
[Quantitative Properties of Graphs#Independant Paths, Connectivity and Cut sets|Independant Paths]: Quantitative Properties of Graphs#independant-paths,-connectivity-and-cut-sets "Independant Paths"
[//end]: # "Autogenerated link references"