1. Combining the results of different scRNA results. 
2. Two types of confounding/batch effects.
	1. Technical variability: changes in sample quality/processing, library prep equipment, or experimental reality. 
	2. Biological variability: patient differences, environmental/genetic perturbation, evolution. 
3. Batch correction:
		![[Screenshot 2024-08-04 at 12.13.06 PM.png]]
		Most correction methods: focused on joint dimension reduction and graph-based joint clustering. 
4. Joint-clustering:
	1. Mutual Nearest Neighbors: given two elements nearest in batch 2, what is the nearest in batch 1?
		1. Produces correction vectors. ![[Screenshot 2024-08-04 at 12.19.19 PM.png]]
	2. Why do we pool experiments and integrate data?
		1. Overcome batch effects, and produce more statistically powerful results for diff exp.
	3. CCA: PCA for two datasets, find axes that create the greatest variation within the dataset and therefore reduce dimensionality. 
		1. ![[Screenshot 2024-08-04 at 12.33.42 PM.png]]
		2. Use nearest neighbors to do classification: label transfer.
		3. **How does this nearest neighbor algorithm actually work**
5. Another method: LIGER
	1. Linked Inference of Genomic Experimental Relationships
	2. Use integrative non-negative matrix factorization: learn a shared, low-dimensional space. 
	3. Joint clustering on this shared factor neighborhood graph (essentially cluster on a low-feature space).
	4. ![[Screenshot 2024-08-04 at 12.43.59 PM.png]]
6. Qualitative (visualize), quantitative (silhouette score, kBET)
	1. Silhouette score:
			![[Screenshot 2024-08-04 at 12.48.26 PM.png]]
	2. kBET: ![[Screenshot 2024-08-04 at 12.50.09 PM.png]]
1. Multiplexing:
	1. Pool many cells together, mitigate technical effects, identify conditions from output data. 
	2. Demuxlet:
			![[Screenshot 2024-08-04 at 12.54.50 PM.png]]
	3. Cell Hashing:
		1. Put unique molecular identifiers on the cells. 
	4. Main points:
		![[Screenshot 2024-08-04 at 12.58.36 PM.png]]
2. Feature selection:
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