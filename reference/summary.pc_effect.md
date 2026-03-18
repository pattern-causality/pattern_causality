# Summarize Pattern Causality Effect

Provides a summary of the pattern causality effect analysis results.
This function displays the summary statistics for the effects, including
the number of components and the strongest effects.

## Usage

``` r
# S3 method for class 'pc_effect'
summary(object, ...)
```

## Arguments

- object:

  A `pc_effect` object.

- ...:

  Additional arguments passed to the `summary` function.

## Value

Invisibly returns the input object.

## Examples

``` r
# \donttest{
data(climate_indices)
dataset <- climate_indices[, -1]
pc_matrix_obj <- pcMatrix(dataset, E = 3, tau = 1, 
  metric = "euclidean", h = 1, weighted = TRUE, 
  verbose = FALSE)
effects <- pcEffect(pc_matrix_obj)
summary(effects)
#> $effects_summary
#> $effects_summary$positive
#>       received   exerted          Diff
#> mean 124.27885 124.27885 -3.552714e-15
#> sd    14.37416  14.29813  2.839047e+01
#> min  111.68984 110.79557 -2.893929e+01
#> max  140.90400 140.62913  3.010843e+01
#> 
#> $effects_summary$negative
#>       received   exerted          Diff
#> mean 34.694733 34.694733  8.881784e-16
#> sd    8.461353  2.545728  1.073526e+01
#> min  27.064962 31.936029 -1.063687e+01
#> max  44.049820 37.701829  1.065365e+01
#> 
#> $effects_summary$dark
#>        received   exerted      Diff
#> mean 141.026422 141.02642   0.00000
#> sd     6.677246  12.19215  17.70408
#> min  132.031033 125.97470 -19.47157
#> max  147.497723 151.50260  18.28564
#> 
#> 
#> $n_components
#> [1] 4
#> 
#> $strongest_effects
#> $strongest_effects[[1]]
#> $strongest_effects[[1]]$component
#> [1] "PNA"
#> 
#> $strongest_effects[[1]]$effect
#> [1] 30.10843
#> 
#> 
#> $strongest_effects[[2]]
#> $strongest_effects[[2]]$component
#> [1] "AAO"
#> 
#> $strongest_effects[[2]]$effect
#> [1] 10.65365
#> 
#> 
#> $strongest_effects[[3]]
#> $strongest_effects[[3]]$component
#> [1] "PNA"
#> 
#> $strongest_effects[[3]]$effect
#> [1] -19.47157
#> 
#> 
#> 
#> attr(,"class")
#> [1] "summary.pc_effect"
# }
```
