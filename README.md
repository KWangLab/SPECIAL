# SPECIAL: Spatial transcriptomics cEll-Cell Interaction ALgorithm
**Last Updated: 09/24/2024**
<img src="https://github.com/kwangcb/IRIS/blob/main/4-Figure/figures/biorender/png/SPECIAL%20%5Bnc%20acc%5D.png" alt="grouping">

## Overview
To quantify the activity of cell-type-specific ligand-receptor interactions within each spatial transcriptomics slide, we further developed our **```R```** single-cell ligand-receptor inference tool called [**SOCIAL**](https://github.com/KWangLab/SOCIAL), into **SPECIAL** (**SP**atial c**E**ll-**C**ell **I**nteraction **AL**gorithm). This novel iteration is customized specifically for spatial transcriptomics with aligned single-cell transcriptomes, the direct output of [**CytoSPACE**](https://github.com/digitalcytometry/cytospace/tree/main). It consists of three major steps: Step I utilizes either a sliding window or k-means clustering approach on bulk (i.e. Visium 10X and Legacy) and SlideSeqV2 spatial transcriptomics, respectively, to divide spatial slides into “regions” of approximately 250 μm in diameter. Step II employs SOCIAL steps 1 through 3 to infer cell-type-specific interaction activity within each ~250 μm region. Step III, ligand-receptor interactions are further denoted as significantly activated if the average expression levels of both the ligand and receptor genes within the respective cell type is greater than the median across all regions. The final output of SPECIAL is a cell-type-specific ligand-receptor interaction activity profile across all regions in a spatial transcriptomics slide.

## Installation
```r
install.packages('devtools')
library(devtools)
devtools::install_github("KWangLab/SOCIAL")
devtools::install_github("KWangLab/SPECIAL")
```
## Tutorials
* To implement SPECIAL in a single spatial transcriptomics slide, see: https://github.com/KWangLab/SPECIAL/blob/main/vignettes/SPECIAL.Rmd
* To implement SPECIAL in a cohort of single spatial transcriptomics slide, see: https://github.com/KWangLab/SPECIAL/blob/main/vignettes/SPECIAL_cohort.Rmd

## Sample data availability
Sample SPECIAL relevant data can be found at https://zenodo.org/records/13172848.

## System requirements
SPECIAL was developed on R (v4.4.1) using R packages: dplyr (v1.1.4), magrittr (v2.0.3), parallel (v4.4.1), pROC (v1.18.5), rBayesianOptimization (v1.2.1), tidyr (v1.3.1), abind (v1.4-5), Matrix (v1.7-0),  urr (v1.0.2), reshape2 (1.4.4), rslurm (v0.6.2), and stats (v4.4.1). All analyses were done on R (v4.4.1).

## Citation
If using SPECIAL, please cite:

Sahni, S., Wang, B., Wu, D. et al. A machine learning model reveals expansive downregulation of ligand-receptor interactions that enhance lymphocyte infiltration in melanoma with developed resistance to immune checkpoint blockade. Nat Commun 15, 8867 (2024). [https://doi.org/10.1038/s41467-024-52555-4](https://rdcu.be/dXbLv)

[Download Citation](https://citation-needed.springer.com/v2/references/10.1038/s41467-024-52555-4?format=refman&flavour=citation)

## Acknowledgement(s)
### Lead Developer(s)
1. **Sahil Sahni**
2. **Kun Wang** (kwang222@illinois.edu)^
3. **Eytan Ruppin** (eytan.ruppin@nih.gov)^

^*equally-contributing corresponding author(s)*

### Acknowledgement(s)
SPECIAL figure was created with BioRender.com.

