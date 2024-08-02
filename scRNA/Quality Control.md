- Data needs to be filtered before clustering process. 
- Transcriptional bursting: genes are only on for time periods (due to activators).
	- Cyclic process, perhaps **application of time series data?**
- Stochastic gene expression: randomness in RNA production from seen above.
- Bulk RNA seq: not evident because there is averaging of all production.
- scRNA: obvious because you only consider a single cell. 
	- Causing sparse matrices.
- **What is the actual pipeline?**
	- Here, raw data is mapped, and then matrices generated, and then quality control?
	- Doesn't it make sense to do QC before count matrices are generated?
- Cell dissociation: important for single cell.
	- You don't want cells with RNA leakage.
	- Dissassociation: damages cells, incomplete causes cell stickage. 
	- RNA leakages can cause additional expression in other cells.
	- Remove background through **SoupX** package.
- Single Cell Capture:
	- Empty wells/droplets.
	- Damage cells if sorting too long.
	- ![[Screenshot 2024-08-02 at 3.50.00 PM.png]]
- Doublets: incorrect libraries generated from two cells due to issues in cell sorting or capture. 
	- Mixed signatures occur due to some type of reaction
- **How do doublets detection algorithms work?**
- Detecting doublets:
	- High number of UMIs.
	- Cluster and then see if cells have signatures from multipleclusters.
	- Combination of such two.
	- **What are suspension conditions?**
	- **What is a heterogeneous tissue?**
	- **How does graphical doublet analysis work?*

* Lysis: major limiting step in terms of the damage that may occur.
* Reverse transcription: another major limiting step.
	* Not a one-on-one relationship due to randomness (RNA sequence always generates the right DNA)
* The actual sequencing machine may also be inconsistent.
	* Also change of index hopping: libraries that are denoted with molecular tags/bar-codes have members that incorrectly go to other libraries due to some intermediate difficulty. 
* **What is the purpose of spike-in RNAs?**
	* Is it just control?
* Different quality control metrics:
	* Mapping statistics (% of unique mapped sequences).
		* Low number of reads -> not neough information for the cell.
		  Bad mapping -> failed library prep (more primer dimers, so less maps).
	* Fraction of exon mapping reads.
	* 3' bias (what does this mean).
		* We read from the 3' end.
		* If there is a high proportion of reads that map to the 10-20% edge of the 3' end of the transcript, bias. 
		* **Need to look at further explanation. **
	* mRNA-mapping reads.
	* Number of UMIs/reads.
	* Number of detected genes.
		* number of detected genes corresponds to the size of the cells (careful if working with cells that have varying sizes).
		* **What is forward scattering?**
	* Spike-in detection.
		* Number of spike-in low --> failed library prep.
		* Proportion of cell to spike-in reads: shows how much starting RNA there is from the cell. 
	* Mitochondrial read fraction, ribosomal read fraction.
		* If you have high mitochondrial RNA, apoptosis may have occurred.
		* This is because in lysis, the cell membrane RNA will be lost, but not the mitochondria.
		* RNA degradation --> leads to more rRNA fragment templating.
			* Enables definition of cell types through rRNA fragment type.
	* rRNA read fraction.
	* Pairwise correlation to other cells. 
* Look at cell distributions in order to make cutoffs.
* Use PCA to look at outliers.
* **In these graphs, what are we measuring?**
	* ![[Screenshot 2024-08-02 at 4.32.21 PM.png]]
* This was cell selection and cell quality control.
* Filtering genes.
	* Look at what genes to choose based on the genes that expressed in cells matching a threshold.
	* Use variable genes (through spike-ins).
	* Filter out genes that have correlation to few other genes.
	* Annotations.
	* Use PCA.
		* **How should one interpret principal components when using PCA here?**
	* High expression: doesn't help in figuring out differentiation or anything. 
		* Outliers.
	