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
2.