# Algorithm S1. Main procedure

```
INPUT:  PLINK binary genotype, one phenotype table per trait, MAF_min, MISS_max, REP, SEED
OUTPUT: association result of the observed phenotype and of each replication

1  G <- prepare_genotype(PLINK binary genotype, MAF_min, MISS_max)
2  for each trait t
3      y_t <- prepare_phenotype(trait table t)
4  end for
5  K <- kinship(G)
6  for each trait t
7      result_obs <- run_emmax(G, y_t, K, "obs")
8      for r = 1 to REP
9          y_r <- permutation of y_t without replacement, seed = SEED + r
10         result_r <- run_emmax(G, y_r, K, "rep r")
11     end for
12 end for
13 return the result files of the observed analysis and of all replications
```
