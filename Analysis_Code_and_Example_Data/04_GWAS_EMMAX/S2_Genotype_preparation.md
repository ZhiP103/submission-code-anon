# Algorithm S2. Genotype preparation

```
INPUT:  PLINK binary genotype (bed / bim / fam), MAF_min, MISS_max
OUTPUT: G (tped / tfam)

1  transpose the PLINK binary genotype into tped / tfam, missing genotype coded as 0
2  drop SNPs whose missing rate exceeds MISS_max
3  drop SNPs whose minor allele frequency is below MAF_min
4  keep materials that carry both genotype and phenotype
5  write the tped and tfam files under one prefix
6  return G
```
