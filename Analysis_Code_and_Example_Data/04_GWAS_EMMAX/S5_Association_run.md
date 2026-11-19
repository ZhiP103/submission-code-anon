# Algorithm S5. Association run and result files

```
INPUT:  G, y, K, tag
OUTPUT: <tag>.ps (SNP id, β, SE(β), p) and <tag>.reml (δ, σ_g², σ_e², h²)

function run_emmax(G, y, K, tag)
1  run EMMAX with the tped / tfam genotype, the phenotype file y and the kinship K
2  collect the per-SNP output: SNP id, β, SE(β) and p
3  collect the variance components: δ, σ_g², σ_e² and h²
4  store the two output files under the tag
5  return (p, β, variance components)
```
