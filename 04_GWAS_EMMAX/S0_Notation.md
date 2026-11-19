# Algorithm S0. Notation

| Symbol | Meaning |
|---|---|
| **G** | genotype in tped / tfam form, one row per material |
| **y** | phenotype vector of one trait, ordered as the tfam samples |
| N | number of materials with both genotype and phenotype |
| M | number of SNPs retained after quality control |
| **K** | kinship matrix between materials, in the kinf form |
| MAF_min | lower bound on minor allele frequency |
| MISS_max | upper bound on per-SNP missing rate |
| β_j | effect size of SNP j |
| p_j | association p-value of SNP j |
| σ_g², σ_e² | genetic and residual variance components |
| δ | ratio of residual to genetic variance |
| REP | number of phenotype permutations run after the observed analysis |
| SEED | fixed random seed of the permutation |
| h² | pseudo-heritability explained by the kinship matrix |

Algorithms

```
S1 — main procedure
S2 — genotype preparation
S3 — phenotype preparation
S4 — kinship matrix
S5 — association run and result files
```
