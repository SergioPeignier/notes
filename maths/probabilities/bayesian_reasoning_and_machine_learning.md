# Probabilistic reasoning

## Probability Refresher

 + Domain of a variable x: dom(x) denotes the states x can take
 + Distribution: Probability values of each state
 + Events: expression of random variables
 + Mutally exclusive: If 2 events cannot be true at the same time
 + $p(x or y) = p(x) + p(y) - p(x and y)$
 + $p(x,y) = p(x and y)$
+ Marginalization: $p(x) = sum_x p(x,y)$
+ Bayes rule: $p(x|y)p(y) = p(x,y)$
+ Density function: for continuous variable x $p(a<x<b) = int_a^bf(x)dx$
+ $p(x=X) = int_{x\in\Delta}f(x)dx$. Then only a common prefactor $\Delta$ exists => It is possible to ignore it since only relative probabilities willbe relevant
+ Unconditional Independence <=> $p(x,y) = p(x)p(y)$ or $p(x|y)=p(x)$ and $p(y|x)=p(y)$
+ Conditional Independence: $X \perp Y|Z$  iif $p(X,Y|Z) = p(X|Z)p(Y|Z) \forall X,Y,Z$: Given z, x does not give more information about y and vice-versa
+ Dependence is noted $X\intercal Y$ 
+ $a \prep b$ and $c \prep b$ does not imply $a \prep c$ (same for dependence)
+ Join distribution table containing $P(x,y,z...)$ contains all the required information.

## Probabilistic Reasoning
+ If we have $P(ill)$ vey low,  $P(food|ill)$ high: $P(ill|food)$ will be very low if $P(food)$ is high and very high if $P(food)$ is low (example 1.2)
+ Notice the difference between prior and posterior $p(knife|knife)=\frac{p(knife,knife)}{p(knife)}=1$ (example 1.3) 
+ Possible operations:
	+ Expand/reduce using bayes formula: $P(a,b,c)=P(a|b,c)p(b| c)P(c)$
	+ Marginalize: $P(a,b) = \sum_c P(a,b,c)$

# Prior, Likelihood and Posterior
+ $D$ : Data observed, $\theta$ : possible scenarios
+ $p(\theta |D ) = \frac{p(D|\theta)p(\theta)}{ \sum\_ \theta p(D| \theta) p(\theta) }$
+ $P(D|/theta)$ : Generative model
+ $P(\theta)$ : Prior
+ $P(\theta| D)$ : Posterior
+ Most probable a posteriori (MAP): $\theta^{map} = argmax(p(\theta | D,M)) 

# Basic Graph Concepts

## Graphs
+ Two variables are dependent if they are linked by a path on the graph
+ Family of a node: node itself and its parents
+ Markov blanket: the node, its parents, children and the parents of its children
+ Directly Acyclic Graph (DAG): Acyclic condition prevents circular reasoning
+ Clique: subset of vertices fully connected: variables that are all dependent on each other
+ Connected graph: if there is a path between every set of vertices
+ singly-connected: only one path from a vertex a to another vertex b
otherwise: multiply-connected
+ Spanning Tree: singly-connected subset of the existing edges such that the resulting singly- connected graph covers all vertices of G. 
+ Maximal spanning tree: With maximal sum of weights

## Numerically encoding graphs

+ edge list
+ Adjacency matrix
+ Adjacency matrix powers: specify how many paths there are from node i to node j in k edge hops
+ Clique matrix: clique matrix is an N×K matrix in which each column ck has zeros except for ones on entries describing the clique
+ Cinc = Incidence matrix: A cliquo matrix containing only two-vertex cliques
+ Cinc Cinc^T is equal to the adjacency matrix except that the diagonals now contain the degree of each vertex 

# Discrete-state Markov Models

 