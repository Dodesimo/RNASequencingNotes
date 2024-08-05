1. What does a typical workflow look like?
2. ![[Screenshot 2024-08-04 at 1.24.38 PM.png]]
3. Why do we do dimensionality reduction:
	1. Simplify complexity.
	2. Remove redundancies.
	3. Identify relevant information.
	4. Reduce computational time.
	5. Facilitate clustering.
	6. Do easy data visualization.
4. ![[Screenshot 2024-08-04 at 1.27.07 PM.png]]
5. PCA Decomposition:
	1.![[Screenshot 2024-08-04 at 1.29.03 PM.png]]
	2. First, z-score.
	3. Then, find two axes where one causes greatest variation, other is orthagonal to it.
	4. Rotate data to these axes. 
	5. ![[Screenshot 2024-08-04 at 1.33.14 PM.png]]
1. Bioinformatics graphs:
	1. Edges represent proximity between cells (correlation, euclidean, etc.)
	2. How does graph-based dimensionality reduction work:
		1. Weighted graph that has top K connections.
		2. Low dimensional version of this graph is computed and optimized. 
2. tSNE = t-stochastic Neighborhood Embedding. 
	1. Distance based on neighbors.
	2. Probability that point i would pick point j as nearest neighbor needs to be the same for a low dimensional space and a high dimensional space. 
	3. Utilizes Kullback-Leibler divergence between complex dimensional space and smaller dimensional space in order to assess random placement of ![[IMG_3080.heic]]points on a line. 
		1. Loss function. 
	4. Neural network type of model: therefore, stochastic.
	5. Cost function focused on minimization of local minima. 
3. UMAP: unifold manifold approximation and projection.
	1. Based on topological structures (simplexes).
	2. ![[Screenshot 2024-08-04 at 1.49.29 PM.png]]
	3. Project to higher dimension manifold:
		![[Screenshot 2024-08-04 at 1.51.22 PM.png]]