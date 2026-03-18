# Print Pattern Causality Effect

Prints the pattern causality effect analysis results. This function
displays the received and exerted influences for each item for positive,
negative, and dark causality types.

## Usage

``` r
# S3 method for class 'pc_effect'
print(x, ...)
```

## Arguments

- x:

  A `pc_effect` object.

- ...:

  Additional arguments passed to the `print` function.

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
print(effects)
#> Pattern Causality Effect Analysis
#> --------------------------------
#> 
#> Positive Causality Effects:
#>     received exerted   Diff
#> AO    131.66  113.90  17.76
#> AAO   111.69  140.63 -28.94
#> NAO   112.86  131.79 -18.93
#> PNA   140.90  110.80  30.11
#> 
#> Negative Causality Effects:
#>     received exerted   Diff
#> AO     28.02   35.74  -7.73
#> AAO    44.05   33.40  10.65
#> NAO    39.64   31.94   7.71
#> PNA    27.06   37.70 -10.64
#> 
#> Dark Causality Effects:
#>     received exerted   Diff
#> AO    140.32  150.36 -10.04
#> AAO   144.26  125.97  18.29
#> NAO   147.50  136.27  11.23
#> PNA   132.03  151.50 -19.47
#> 
# }
```
