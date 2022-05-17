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

## Part 4 Discussion and Conclusion
For this project, I loaded a large data set of authors and co-authors into a graph using the igraph package in R. Since this dataset contained over 5000 nodes and 14000 edges, it was clear I would need to implement some graph simplification strategies. 

I applied multiple strategies before successfully completing our simplification. Firstly, I order my nodes based on frequency and selected the top 300 authors. This strategy helped simplify our graph, but I am concerned this would not have enough randomness within the sample. Instead, I selected 400 nodes randomly, and then reduced this number by mandating the nodes have at least one degree. This strategy performed better, but resulted in a graph containing two subgraphs, and I preferred to work with just one. The final strategy had me performing degree removal first, dropping all nodes with less than 20 degrees, then I took the first 200 nodes of the resulting graph and dropped the remaining nodes with less than 2 degrees. The result was the graph shown in Figure 5, which contains 46 vertices, 105 edges, and no subgraphs, this is the graph I used for the remainder of my analysis.

The rest of our analysis includes practicing with the igraph functions mentioned in the rubric, as well as some others. This exploration helped me become much more comfortable working with, visualizing, and understanding graph. The functions made it easier for me to identify and label cliques that occurred within the dataset. I also learned how to use different measurements for centrality, including closeness, betweenness, alpha, and power centrality. Finally, I learned the difference between directional measurements, such as hubs and authorities, and how to represent them in my graph. 
