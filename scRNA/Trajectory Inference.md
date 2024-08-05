1. Trajectory done before diff exp, or multiple paths.
	1. ![[Screenshot 2024-08-05 at 4.46.39 PM.png]]
2. Trajectory time: time cell takes in a differentiation process. 
	1. Cells show a continuous spectrum of states. 
3. Individual cells differentiate unsynchronized way.
4. Pseudotime: arbitrary unit of measurement.
5. **you need to make sure there  is a development trajectory in your data.**
6. **need to see if there are intermediate steps, and if there is branching in your trajectory**.
7. Any dataset can be forced into trajectory, but not necessarily biological. 
8. Need to capture what you expect. Types of  trajectory models. ![[Screenshot 2024-08-05 at 4.50.36 PM.png]]
9. Trajectory pipelines:
	1. ![[Screenshot 2024-08-05 at 4.51.07 PM.png]]
10. ICA: independent component analysis
	1. Decompose to individual signels. 
	2. ![[Screenshot 2024-08-05 at 4.52.38 PM.png]]![[Screenshot 2024-08-05 at 4.54.11 PM.png]]
11. Diffusion Maps
	1. Distance between points A and B is the probability of going through the nodes with K steps.
	2. Assuming intermediate point, if probability A to int is equal to int to B, A and B are well connected through that point. 
12. Minimum Spanning Tree
	1. Classic CS
	2. Djikstras, create a set of connections between points such that the sum of of all the distances is minimized. ![[Screenshot 2024-08-05 at 5.03.08 PM.png]]
13. MST challenge: very reliant on individual points.
	1. Cluster cells, and then do trajectory analysis. ![[Screenshot 2024-08-05 at 5.06.58 PM.png]]![[Screenshot 2024-08-05 at 5.08.15 PM.png]] Reverse graph embeddding![[Screenshot 2024-08-05 at 5.09.31 PM.png]]
	2. Whole timeline above. 
	3. RNA Velocity: uses proportion  of spliced/unspliced reads to predict cell's future state. ![[Screenshot 2024-08-05 at 5.15.48 PM.png]]![[Screenshot 2024-08-05 at 5.16.57 PM.png]]