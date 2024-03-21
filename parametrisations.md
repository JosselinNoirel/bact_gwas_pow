# Remarquable parametrisations

This parametrisation provides 5 true positives out of 30 hits detected at the 25% FDR level.

```r
n = 30             # Number of causal genes
N = 5000           # Number of genes to be tested

f = rep(.25, n)     # Minor allele frequency (let's assume constant)
beta = rep(1, n)   # Arbitrary effect size for all genes

h2 = .5

alpha = .05
fdr_thr = .25
P = .8 # Capital "P"
P = 1 - (1 - P)^(1/n)

K = 473 # From power.t.test() + unequal-size group correction
```

Even better:

```r
n = 30             # Number of causal genes
N = 5000           # Number of genes to be tested

f = rep(.25, n)     # Minor allele frequency (let's assume constant)
# beta = rep(1, n)   # Arbitrary effect size for all genes
beta = 1:n

h2 = .5

alpha = .05
fdr_thr = .5
P = .8 # Capital "P"
P = 1 - (1 - P)^(1/n)

K = 223
```

