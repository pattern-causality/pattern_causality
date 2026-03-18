# Summarize Pattern Causality Matrix

Provides a summary of the pattern causality matrix object. This function
calculates and displays descriptive statistics (mean, SD, min, max) for
each causality matrix (positive, negative, dark).

## Usage

``` r
# S3 method for class 'pc_matrix'
summary(object, ...)
```

## Arguments

- object:

  A `pc_matrix` object.

- ...:

  Additional arguments passed to the `summary` function.

## Value

Invisibly returns the input object.

## Examples

``` r
data(climate_indices)
dataset <- climate_indices[, -1]
pc_matrix_obj <- pcMatrix(dataset, E = 3, tau = 1, 
  metric = "euclidean", h = 1, weighted = TRUE, 
  verbose = FALSE)
summary(pc_matrix_obj)
#> Pattern Causality Matrix Summary:
#> 
#> Number of items: 4 
#> 
#> Matrix statistics:
#>              Type   Mean     SD    Min    Max
#> Positive Positive 0.4143 0.0657 0.3189 0.5194
#> Negative Negative 0.1156 0.0402 0.0722 0.2090
#> Dark         Dark 0.4701 0.0597 0.3811 0.5552
```
