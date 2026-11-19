# Algorithm S4. Kinship matrix

```
INPUT:  G (one tped / tfam prefix)
OUTPUT: K in kinf form

1  read the tped / tfam files of the genotype prefix
2  compute the Balding-Nichols kinship coefficient for every pair of materials
3  assemble the pairwise coefficients into K (N × N)
4  write K as <prefix>.aBN.kinf
5  return K
```
