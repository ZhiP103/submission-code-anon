# Analysis Code and Example Data

This repository contains the analysis procedures and example data for UAV LiDAR-based
phenotyping of cotton. All procedures are provided as step-wise algorithm descriptions in
Markdown, covering point cloud processing, curve fitting, machine learning modelling and
genome-wide association analysis.

```
Analysis_Code_and_Example_Data/
├── 01_LiDAR_PointCloud_Processing/   Point cloud processing
├── 02_Curve_Fitting_Models/          Curve fitting models
├── 03_Machine_Learning_Models/       Machine learning models
├── 04_GWAS_EMMAX/                    Association analysis
└── 05_Phenotypic_Data/               Example data
```

## Description of the folders

**01_LiDAR_PointCloud_Processing** — Procedures for plot-wise processing of the LiDAR point
clouds and for deriving canopy structural traits from the processed point clouds.

**02_Curve_Fitting_Models** — Procedures for fitting the time series of phenotypic traits with
several candidate models, comparing their fit, and extracting dynamic trait parameters from the
selected model.

**03_Machine_Learning_Models** — Procedures for constructing regression and tree-based models,
training and validating them, and evaluating their predictive performance.

**04_GWAS_EMMAX** — Procedures for genome-wide association analysis of the phenotypic traits,
from input preparation through to the association results.

**05_Phenotypic_Data** — Example files for the folders above, including point clouds and
phenotype files.
