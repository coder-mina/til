# Ch.10 Mining Social-Network Graphs

k-partite graph = graph consisting of k disjoint sets of nodes, with no edges between nodes of the same set.

clique = a set of nodes with edges between any two of them.

complete bipartite graph = Ks,t = consists of s nodes on one side and t nodes on the other side, with all st possible edges between the nodes of one side and the other present.



importan aspect of social networks is that they contain communities of entites that are connected by many edges.

We would like to detect communities. But using standard clustering algorithms have problems.

So we use specialized clustering techniques to find communities in social networks.



betweenness of an edge (a, b) = number of pairs of nodes x and y such that the edge (a, b) lies on the shortest path between x and y. High betweenness means that edge (a, b) runs between two different communities. 



## 10.3 Find communities

* Girvan-Newman algorithm
* edge removal: remove edges with the highest betweennes until the graph has broken into a suitable number of connected components.
* finding complete bipartite graphs: (use complete bipartite subgraphs for community finding in ordinary graphs )

## 10.4 Partitioning

* partitioning is another approach to organizing social network graphs.
* We would like to partition a graph to minimize the number of edges that connect different components. ( = cut)
* cut = set of edges that connect nodes in different sets.
* good partition = cut is minimized && two sets are approximately equal in size. => so, we use "normalized cut"
* ???

## 10.5 Finding overlapping communities

* we take a social graph and try to fit a model to it that best explains how it could have been generated. (maximum likelihood estimation (MLE))

* 
* 
* 
*  We make an assumption about the generative process that creates instances of some artifact. The model has parameters that determine the probability of generating any particular instance of the artifact. This probability is called the likelihood of those parameter values. We assume that the value of the parameters that gives the largest value of the likelihood is the correct model for the observed artifact.