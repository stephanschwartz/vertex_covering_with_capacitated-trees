### Online Supplement of

# Vertex Covering with Capacitated Trees

#### Ralf Borndörfer, Stephan Schwartz, and William Surau

Zuse Institute Berlin, Takustr 7, 14195 Berlin

---

This online supplement provides instances and detailed results of the computational experiments conducted for the paper "Vertex Covering with Capacitated Trees". A preprint is available as [technical report](https://opus4.kobv.de/opus4-zib/frontdoor/index/index/docId/8261) published by Zuse Institute Berlin, 2021 and all details concerning this version are located in the "preprint" directory.

## Instances
For the computational study, we generated two types of random transit networks with artificial traffic volume: random trees, and random networks based on Voronoi diagrams.
We provide here the original transit networks as well as the line graph versions (labelled with "_lg") . The instances are generated with our [transit network generator](https://github.com/stephanschwartz/transit_network_generator).

#### Trees
The 25 tree instances are built from random points in a rectangle by using
Kruskal's algorithm on the complete graph with Euclidean edge weights.
The assigned traffic is a combination of random origin-destination traffic and
traffic obtained by a gravity model.

#### Voronoi Networks
For these instances, we create a Voronoi diagram and 
consider the graph that is spanned
by the ridges between the Voronoi cells. This is our basic Voronoi
graph with Euclidean edge lengths. Now, we add additional
random leaves, split the edges to obtain a specified number of
nodes, and stretch each edge by a random factor.
The artificial traffic is generated as for the random trees.
The 50 generated instances are split into two groups: 33 of medium size and 17 large instances.

#### How to load an instance (in Python using networkx)
```
import networkx as nx
path_to_file = 'instances/tree/tree_1.graphml'
graph = nx.read_graphml(path_to_file, node_type=int)
```

## Detailed Results
We present detailed results of our computational study for all generated instances. In particular we report on the following outputs that are explained in the paper.

* instance properties:

   - number of nodes
   - number of edges
   - treewidth
   - fraction of edges that are bridges
   - planarity of the graph

Computation times for

* connectivity formulations

   - single-commodity flow (SCF)
   - multi-commodity flow (MCF)
   - rooted arc separators (RAS)
   - rooted node separators (RNS)
   - coarse-to-fine flow (C2F)

* algorithmic enhancements

   - heuristic for the pricing problem (H)
   - median induced preprocessing (P)
   - local search (L)

* branch-and-price approach

   - number of branching nodes
   - B&P-time
   - root solution time
   - gap after B&P
   - gap for root solution
 
For the computation times, a time limit of 24 hours (i.e., 86400 seconds) was set.
