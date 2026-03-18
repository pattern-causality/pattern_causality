# Print Pattern Causality Cross Validation Results

Prints the pattern causality cross-validation results. This function
displays the parameters used for cross-validation, the sample sizes, and
the summary statistics.

## Usage

``` r
# S3 method for class 'pc_cv'
print(x, ...)
```

## Arguments

- x:

  A `pc_cv` object.

- ...:

  Additional arguments passed to the `print` function.

## Value

Invisibly returns the input object.

## Examples

``` r
data(climate_indices)
X <- climate_indices$AO
Y <- climate_indices$AAO
numberset <- c(100, 150, 200)
cv_results <- pcCrossValidation(X, Y, 3, 2, "euclidean", 1, FALSE, numberset = numberset)
print(cv_results)
#> Pattern Causality Cross-Validation Results
#> ----------------------------------------
#> Parameters:
#>   Embedding dimension (E): 3 
#>   Time delay (tau): 2 
#>   Metric: euclidean 
#>   Horizon (h): 1 
#>   Weighted: FALSE 
#>   Random: TRUE 
#>   Bootstrap: 1 
#> 
#> Sample sizes: 100, 150, 200 
#> 
#> Results:
#>     positive negative   dark
#> 100   0.4848   0.0606 0.4545
#> 150   0.4250   0.0500 0.5250
#> 200   0.3088   0.1029 0.5882
```
