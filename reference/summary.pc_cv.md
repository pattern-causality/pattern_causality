# Summary of Pattern Causality Cross Validation Results

Provides a summary of the pattern causality cross-validation results.
This function calculates and displays summary statistics for the
cross-validation results, including sample statistics, causality
statistics, and convergence.

## Usage

``` r
# S3 method for class 'pc_cv'
summary(object, ...)
```

## Arguments

- object:

  A `pc_cv` object.

- ...:

  Additional arguments passed to the `summary` function.

## Value

Invisibly returns the input object.

## Examples

``` r
data(climate_indices)
X <- climate_indices$AO
Y <- climate_indices$AAO
numberset <- c(100, 150, 200)
cv_results <- pcCrossValidation(X, Y, 3, 2, "euclidean", 1, FALSE, numberset = numberset)
summary(cv_results)
#> $parameters
#> $parameters$E
#> [1] 3
#> 
#> $parameters$tau
#> [1] 2
#> 
#> $parameters$metric
#> [1] "euclidean"
#> 
#> $parameters$h
#> [1] 1
#> 
#> $parameters$weighted
#> [1] FALSE
#> 
#> $parameters$random
#> [1] TRUE
#> 
#> $parameters$bootstrap
#> [1] 1
#> 
#> $parameters$n_cores
#> [1] 1
#> 
#> $parameters$relative
#> [1] TRUE
#> 
#> 
#> $sample_stats
#>    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
#>     100     125     150     150     175     200 
#> 
#> $causality_stats
#> NULL
#> 
#> $convergence
#>     value 
#> 0.1966815 
#> 
#> attr(,"class")
#> [1] "summary.pc_cv"
```
