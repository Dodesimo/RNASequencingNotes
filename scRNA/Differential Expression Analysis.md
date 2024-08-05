What is this?
- Take read count data.
- Do statistics to discover changes in expression levels between experimental groups.
- Decide whether this difference is statistically significant.
What the data looks like:
- ![[Screenshot 2024-08-05 at 12.44.31 PM.png]]
* Limitations in the sequencing data:
	![[Screenshot 2024-08-05 at 12.45.04 PM.png]]
* Distribution: looks uneven because expression differs per cell. 
Nonparametric tests:
* Convert expression values to ranks, and tests the distribution of ranks between two groups. 
* May fail due to drop outs. 
scRNA-seq specific methods:
- Relies on clustering to identify cell groups.
Modeling wise:
- ![[Screenshot 2024-08-05 at 12.52.35 PM.png]]
Negative binomial
- ![[Screenshot 2024-08-05 at 12.54.49 PM.png]]![[Screenshot 2024-08-05 at 12.55.49 PM.png]]
Zero-inflated negative binomial:
* Accounts for dropout. ![[Screenshot 2024-08-05 at 12.59.39 PM.png]]
Poisson Beta
![[Screenshot 2024-08-05 at 1.00.33 PM.png]]
![[Screenshot 2024-08-05 at 1.00.52 PM.png]]
Important metrics:
- ![[Screenshot 2024-08-05 at 1.04.40 PM.png]]
- Greater sensitivity, lower specificity. ![[Screenshot 2024-08-05 at 1.15.34 PM.png]]