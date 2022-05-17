# Arxiv GR-QC Graph Analysis
RStudio graph analysis, based on the dataset of Arxiv GR-QC (General Relativity and Quantum Cosmology) collaboration network.

## Description
Arxiv GR-QC (General Relativity and Quantum Cosmology) collaboration network is from the e-print arXiv and covers scientific collaborations between authors papers submitted to General Relativity and Quantum Cosmology category. If an author i co-authored a paper with author j, the graph contains a undirected edge from i to j. If the paper is co-authored by k authors this generates a completely connected (sub)graph on k nodes.
The data covers papers in the period from January 1993 to April 2003 (124 months). It begins within a few months of the inception of the arXiv, and thus represents essentially the complete history of its GR-QC section.

Source (citation)
• J. Leskovec, J. Kleinberg and C. Faloutsos. Graph Evolution: Densification and Shrinking Diameters. ACM Transactions on Knowledge Discovery from Data (ACM TKDD), 1(1), 2007.

![1652804234(1)](https://user-images.githubusercontent.com/90291484/168859724-d45bcc0e-6a60-43f3-a0a4-a1bf25829a8d.png)

## Part 1 Dataset Loading
The nodes are authors without identification. Edges represent co-authorship.
The first few entries look like this:

  FromNodeId	ToNodeId
  
  3466	      937
  
  3466	      5233
  
  3466	      8579
  
  3466	      10310
  
So, author 3466 had multiple collaborations.

## Part 2 Initial Graph Plotting and Simplifying
Initially created the plot for the entire dataset, I can hardly observe the data structure (Figure 1). So I took the three steps towards graph simplification: 

• Step 1. Choose the nodes with degree greater than or equal to 20 and plot the graph (Figure 2).

• Step 2. Choose the first 200 edges and plot the graph (Figure 3).

• Step 3. Choose the nodes with degree larger than 2 and plot the graph (Figure 4).

Finally, I arrive at a three-cluster igraph object for deeper analysis and plotting.

## Part 3 Explore Functions
Applied functions from igraph package to show the following information of the dataset:

• Vertices of the Graph

• Edges of the Graph

• Adjacency Matrix

• Density

• Egocentric Network and Degrees

• Betweenness Centrality

• Closeness Centrality

• Shortest Paths

• Geodesic

• Number of Paths Between Nodes

• Degree Histogram

• Diameter

• Max Cliques

• Largest Cliques

• Alpha Centrality

• Walktrap Communities

• Look at more available layouts

• Heatmap of the Network Matrix

• Reciprocity

• Transitivity

• Eigenvector

• Average path length

• Hubs Score

• Authorities Score

• Central Node

• Longest Path

• Largest Clique

• Power Centrality

