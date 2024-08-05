Cell identity:
- Environmental stimuli
- Cell development
- Cell cycle
- Spatial context
- Determines cell type. 
Cell identification pipeline:
![[Screenshot 2024-08-05 at 12.03.05 PM.png]]
 Feature selection:
	1. Features lose meaning as more exist (curse of dimensionality).
	2. More features --> introduce noise. 
3. Highly variable gene (calculation of CV), fit gamma model.
	1. ![[Screenshot 2024-08-05 at 12.05.42 PM.png]]
	2. Line is a threshold. 
4. M3Drop: dropout-based feature selection
	1. Look at expression level versus dropout rate. ![[Screenshot 2024-08-05 at 12.07.13 PM.png]]
5. Only take into account Principal Components that can be "informative."
6. Hierarchical Clustering. 
	1. Minimize function of variance inside clusters versus variance between clusters. 
	2. Produce dendogram. 
	3. Find closes points, plot distance, then amalgamate points based on closeness. 
	4. ![[Screenshot 2024-08-05 at 12.11.47 PM.png]]
	5. Similarity between clusters:
		1.![[Screenshot 2024-08-05 at 12.12.40 PM.png]]
	6. Similarity between objects in the cluster:
		1. ![[Screenshot 2024-08-05 at 12.15.05 PM.png]]
1. k-means, keep changing prototype through averages, recalculate classification, keep doing till no changes. ![[Screenshot 2024-08-05 at 12.17.53 PM.png]]
2. Graph-based clustering:
	1. Nodes are cells, edges are similarity.
	2. Graph types:
		1. ![[Screenshot 2024-08-05 at 12.18.48 PM.png]]
3. Community detection: 
	1. Find groups of nodes that have more edges internally compared to outside the group.
4. Graph cuts: 
	1. Partition graph into subgraphs. 
	2. ![[Screenshot 2024-08-05 at 12.21.15 PM.png]]
	3. NP Hard.
5. Heruistic:
	1. Spectral clustering
	2. Markov clustering
	3. Louvain
6. SC3
	1. ![[Screenshot 2024-08-05 at 12.23.16 PM.png]]
7. Seurat
	1. ![[Screenshot 2024-08-05 at 12.26.11 PM.png]]
8. Comparing clustering quality:
	1. ![[Screenshot 2024-08-05 at 12.28.06 PM.png]]
9. What are we not sure about:
	1. Cell type, number of clusters.
	2. 