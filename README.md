# Weighted Gene Co-expression Network Analysis (WGCNA)
## ❓ What is WGCNA?
Weighted Gene Co-expression Network Analysis (WGCNA) is a systems biology method used to analyze gene expression data by constructing networks that represent gene co-expression relationships. This approach helps identify clusters of genes with similar expression patterns and explores the relationships between these clusters and external traits or conditions.

WGCNA is particularly useful for identifying gene modules that are associated with complex traits and for gaining insights into the underlying biology of the system being studied.

A typical workflow looks something like this:

![workflow](https://github.com/ndomah001/Weighted-Correlation-Network-Analysis/blob/main/workflow.jpg)

## 📝 Study Design
I will be performing a WGCNA on RNA-seq data of peripheral blood mononuclear cells (PBMCs) from a group of 17 COVID-19 subjects and 17 healthy controls ([GSE152418](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE152418)).

**Goals**:
- Identify what modules (genes or clusters of genes) that are significantly associated with COVID-19 individuals.
- Identify genes that are significantly associated with *severe* COVID-19 cases.

## 📊 Visualizations
### Cluster Dendrogram
- This dendrogram shows the hierarchical clustering of samples (GSM numbers).
- It indicates how similar the gene expression profiles are between different samples. Samples that cluster together have more similar overall gene expression patterns.
- This can help identify potential outliers or groups of samples that behave similarly.

![cd](https://github.com/ndomah001/Weighted-Gene-Co-expression-Network-Analysis/blob/main/1.%20dendrogram.png)

### PCA Plot
- This Principal Component Analysis (PCA) plot, shows the first two principal components (PC1 and PC2) that explain the most variance in the data.
- Each point represents a sample. The spread of points suggests there's variability between samples, but no clear separation between groups is visible.
- This could indicate subtle differences between COVID-19 and healthy samples, or potential confounding factors.

![pca](https://github.com/ndomah001/Weighted-Gene-Co-expression-Network-Analysis/blob/main/2.%20PCA.png)

### Scale-free Topology Fit & Mean Connectivity
These plots help choose the soft-thresholding power for network construction:
- The top plot shows how well the network fits a scale-free topology at different powers.
- The bottom plot shows how the mean connectivity decreases with increasing power.
  
Based on these plots, I will use a power of 18, as it achieves a high scale-free topology fit (R^2 > 0.8) while keeping mean connectivity relatively low.

![sftf&mc](https://github.com/ndomah001/Weighted-Gene-Co-expression-Network-Analysis/blob/main/3.%20power.png)

### Gene Dendrogram and Module Colors
This dendrogram shows the clustering of genes based on their expression patterns. The color bar at the bottom represents different modules:
- The "unmerged" row shows initial module assignments.
- The "merged" row shows final modules after similar ones are combined.
  
There are several distinct modules (colored blocks) that could represent co-expressed gene networks potentially associated with COVID-19 or disease severity.

![gd](https://github.com/ndomah001/Weighted-Gene-Co-expression-Network-Analysis/blob/main/4.%20module%20dendrogram.png)

### Module-Trait Relationships Heatmap
This heatmap shows correlations between module eigengenes and traits:
- Rows represent modules (`ME` = Module Eigengene)
- Columns represent traits (disease state, clinical characteristics)

![mtrh](https://github.com/ndomah001/Weighted-Gene-Co-expression-Network-Analysis/blob/main/5.%20heatmap.png)

## 🔬 Observations
1. Modules significantly associated with COVID-19:
   - Positively associated: `MEyellow`, `MEpurple`, `MEbrown`, `MEpink`
   - Negatively associated: `MEgreen`, `MEblue`, `MEturquoise`

2. Modules/genes potentially associated with severe COVID-19:
   - `MEyellow` and `MEturquoise` show moderate correlations with *severe* cases
   - `MEgreen` shows a strong association with mild/moderate cases, so genes in this module might be protective against severe disease
  
To further my analysis, I should:
1. Examine the genes within these significant modules, particularly `MEyellow`, `MEturquoise`, and `MEgreen`.
2. Perform functional enrichment analysis on these modules to understand the biological processes involved.
3. Identify hub genes within these modules, as they may be key drivers of the COVID-19 response or disease severity.


