# Algorithm S2. Data preparation

```
INPUT:  modelling table
OUTPUT: X (predictor matrix), y (response vector), treatment label of each sample

1  read the modelling table; one row per sample, identifier as the row label
2  y <- biomass column ;  X <- the remaining p phenotypic traits
3  treat non-numeric placeholders as missing ; drop records whose trait set is incomplete
4  derive the treatment label (NN / LN) from the sample identifier
5  return (X, y, label)
```
