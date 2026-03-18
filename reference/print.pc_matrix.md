# Print Pattern Causality Matrix

Prints the pattern causality matrix object. This function displays the
specified causality matrix (or all matrices) with a preview of the first
5 rows and columns.

## Usage

``` r
# S3 method for class 'pc_matrix'
print(x, type = "all", ...)
```

## Arguments

- x:

  A `pc_matrix` object.

- type:

  The type of matrix to print ("all" or "positive", "negative", "dark").

- ...:

  Additional arguments passed to the `print` function.

## Value

Invisibly returns the input object.

## Examples

``` r
data(climate_indices)
dataset <- climate_indices[, -1]
pc_matrix_obj <- pcMatrix(dataset, E = 3, tau = 1, 
  metric = "euclidean", h = 1, weighted = TRUE, 
  verbose = FALSE)
print(pc_matrix_obj, type = "positive")
#> Pattern Causality Matrix Analysis:
#> 
#> Number of items: 4 
#> 
#> Positive causality matrix:
#>            AO       AAO       NAO       PNA
#> AO         NA 0.5124763 0.3919950 0.4121643
#> AAO 0.3914184        NA 0.4065322 0.3189478
#> NAO 0.3749311 0.3768050        NA 0.3768436
#> PNA 0.3726418 0.5170100 0.5193883        NA
```
