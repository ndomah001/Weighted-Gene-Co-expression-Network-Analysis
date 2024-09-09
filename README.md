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
**Cluster Dendrogram**
- This dendrogram shows the hierarchical clustering of samples (GSM numbers).
- It indicates how similar the gene expression profiles are between different samples. Samples that cluster together have more similar overall gene expression patterns.
- This can help identify potential outliers or groups of samples that behave similarly.

![cd](https://github.com/ndomah001/Weighted-Gene-Co-expression-Network-Analysis/blob/main/1.%20dendrogram.png)

**PCA Plot**
- This Principal Component Analysis (PCA) plot, shows the first two principal components (PC1 and PC2) that explain the most variance in the data.
- Each point represents a sample. The spread of points suggests there's variability between samples, but no clear separation between groups is visible.
- This could indicate subtle differences between COVID-19 and healthy samples, or potential confounding factors.

![pca](https://github.com/ndomah001/Weighted-Gene-Co-expression-Network-Analysis/blob/main/2.%20PCA.png)

**Scale-free Topology Fit & Mean Connectivity**


![]()

**Gene Dendrogram and Module Colors**


![]()

**Module-Trait Relationships Heatmap**


![]()

## 🔬 Observations

