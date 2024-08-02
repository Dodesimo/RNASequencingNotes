1. Focused on only one cell. 
2. Sequencing machines: limited by length.
3. Fragmentation: cDNA splitting.
4. UMI:
	1. Sample labeled with UMI (identifier, then amplified). This is because there can be multiple copies of the same genes, and distinguishing them is hard. Thus, they show the original ratio of molecules that were present in the sample. 
	2. Enables creation of families, thus enable patterns to be evident across.
	3. Because there are same UMI assigned to all, you can not lose information.
5. Smart-SEQ2: used for low amounts of cells , full-length.
6. Droplet-based: used for large volumes of cells, full-length not affordable, 
	1. **When do you pick when? Just based on cell amount?**
	2. **What is the difference between a 3' and 5' library? The order they are sequenced in?**
		1. For TCRSeq, 5' libraries enable you greater coverage. 
7. Dropoff exists: more reads, more genes, but not linear.
8. Dropout: RNA exists, but cannot pinpoint what gene it is. 
9. Quality of sequencing: important to verify.
	1. FastQC
	2. Read above Q30
10. Cell calling: seperate cells into clusters based off of their UMI.
	1. **What does high UMI content mean?**
	2. **How are thresholds decided?**
11. Mapping engines: do genomic allignment. 
12. Allignment free quant: RNASkim, eXpress, kallisto, salmon (relies on a hashing function and k-mers (substrings within a longer))
13. So...
	1. Overall pipeline:
		1. Sequencing quality control, cell calling, allignment + expression counting (what generates sam and bam files), then count matrix production.
14. Count matrix is sparse due to dropout.
	1. Most are zeroes, but you can plot clusters through common expression (does this represent a biological subset?)
15. **Is cell hashing just another type of cell calling technique?**
	1. Cells have unique identifiers. 
16. Ribosomal proteins: volatile because cell environment plays important role in its regulation. 
	1. Thus, causes batch effects. 
17. **What is a homotypic and heterotypic doublet?**