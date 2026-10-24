# Cancer Gene Expression Explorer

## Project Overview

This project explores gene-expression differences between breast cancer tissue and normal breast tissue using publicly available gene-expression data.

The aim is to identify genes showing differences in expression between the two groups and explore these patterns using statistical analysis and visualizations.

## Research Question

**Which genes show the clearest expression differences between breast cancer tissue and normal breast tissue in the GSE42568 dataset?**

## Dataset

- **Source:** NCBI Gene Expression Omnibus (GEO)
- **Dataset:** [GSE42568](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE42568)
- **Platform:** Affymetrix Human Genome U133 Plus 2.0 Array (GPL570)
- **Data type:** Gene-expression microarray data

## Methods

The analysis notebook performs the following steps:

1. Retrieves the gene-expression dataset and platform annotation.
2. Maps microarray probes to gene symbols.
3. Selects a representative probe for each gene using across-sample expression variance.
4. Compares expression between cancer and normal tissue samples using Welch's t-test.
5. Applies the Benjamini–Hochberg procedure to adjust for multiple testing.
6. Generates visualizations to explore expression patterns and differences.


## Preliminary Results

The exploratory analysis compared gene-expression profiles from 104 breast tumour samples and 17 normal breast tissue samples in the GSE42568 dataset.

Welch's t-tests were performed for 21,737 genes, followed by Benjamini–Hochberg false-discovery-rate adjustment. Using an FDR q-value threshold of less than 0.05, 8,895 genes met the statistical significance threshold in this analysis. Of these, 5,609 showed higher mean expression in tumour samples, while 3,286 showed higher mean expression in normal samples.

COL10A1, NECTIN4, RAB15, FBXL16 and MMP11 were among the highest-ranked genes by statistical evidence in the exported results. COL10A1 showed a mean expression difference of approximately 3.59 units between tumour and normal samples on the analysis scale.

These findings are exploratory. The results do not establish causation, clinical utility or validated biomarkers. Preprocessing, statistical assumptions, potential confounding and independent reproducibility require further assessment before firm biological conclusions can be drawn.


## Visualizations

The project generates four types of plots:

- Sample median expression
- Top-gene expression boxplots
- Top gene-expression differences
- Volcano plot

## Repository Contents

- `Cancer_Gene_Expression_Explorer_Project1.ipynb` — analysis notebook
- `Cancer_Gene_Expression_Explorer_Results.zip` — exported analysis results and visualizations

## Reproducibility

The analysis was performed in Python using Google Colab. The notebook contains the analysis workflow, and the exported results are provided for inspection.

## Limitations

- This is an exploratory analysis of a single public dataset.
- Differences in gene expression do not establish causation.
- Statistical significance does not necessarily imply biological or clinical significance.
- Results may depend on preprocessing, probe-to-gene mapping, and probe-selection choices.
- Findings require independent validation before being considered robust biomarkers or clinical evidence.

## Responsible Interpretation

This project is an educational bioinformatics analysis. It is not intended for diagnosis, treatment selection, or clinical decision-making.

## Future Work

- Investigate the biological functions and pathways of top-ranked genes.
- Compare findings with an independent breast cancer gene-expression dataset.
- Assess the robustness of the results to alternative preprocessing and analysis choices.
