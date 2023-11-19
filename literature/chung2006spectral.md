---
aliases: [CH 1 Eigenvalues and the Laplacian of a graph]
created: 2023-11-10T10:52:05-08:00
modified: 2023-11-10T11:55:38-08:00
tags: 
---
# CH 1 Eigenvalues and the Laplacian of a graph
## 1.1 Introduction
- Graph theory has often been treated algebraically, through representations of connections between nodes through their adjacency matrix. Eigenvalues often studied as the "algebraic connectivity"
- Recent advances have treated graph theory geometrically by considering the isoperimetric properties and random walks of over the graph.
- Graph eigenvalues link these two views and parallels exist under a unifying framework of spectral graph theory
- "The development of rapidly mixing Markov chains has intertwined with advances in randomized approximation algorithms.
## 1.2 Laplacian and eigenvalues
- We only consider normalized eigenvalues for graphs
	- More relevant to other areas such as spectral geometry and stochastic processes
>[!def graph adjacency matrix]
>Let graph $G$ simple graph without loops and $d_v$ denote the degree of vertex $v$. Then the normalized adjacency matrix $L$ is
>$L(u, v)=\left\{\begin{array}{cl}d_v & \text { if } u=v \\ -1 & \text { if } u \text { and } v \text { are adjacent } \\ 0 & \text { otherwise. }\end{array}\right.$

>[!def graph laplacian]
>Let graph $G$ simple graph without loops and $d_v$ denote the degree of vertex $v$. Then the graph laplacian
>$$\mathcal{L}(u, v)=\left\{\begin{array}{cl}1 & \text { if } u=v \text { and } d_v \neq 0 \\ -\frac{1}{\sqrt{d_u d_v}} & \text { if } u \text { and } v \text { are adjacent } \\ 0 & \text { otherwise. }\end{array}\right.$$

>[!prop the laplacian equivalent to the adjacency matrix]
>- $\mathcal{L}(u,v) = \mathcal{L}=T^{-1 / 2} L T^{-1 / 2}$
>- $T$ denotes the diagonal matrix of vertex degrees with the convention $T^{-1}(v, v)=0$ for $d_v=0$.

[todo::review page 3 again]
