# Pattern Causality Matrix Object

Creates a pattern causality matrix object. This function constructs an
object of class `pc_matrix` containing the positive, negative, and dark
causality matrices, along with item names.

## Usage

``` r
pc_matrix(
  positive = NULL,
  negative = NULL,
  dark = NULL,
  items = NULL,
  verbose = TRUE
)
```

## Arguments

- positive:

  Positive causality matrix.

- negative:

  Negative causality matrix.

- dark:

  Dark causality matrix.

- items:

  Names of items in the matrices.

- verbose:

  Logical, whether to print progress information.

## Value

An object of class "pc_matrix".

## Examples

``` r
data(climate_indices)
dataset <- climate_indices[, -1]
pc_matrix_obj <- pcMatrix(dataset, E = 3, tau = 1, 
  metric = "euclidean", h = 1, weighted = TRUE, 
  verbose = FALSE)
print(pc_matrix_obj)
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
#> 
#> Negative causality matrix:
#>             AO        AAO        NAO        PNA
#> AO          NA 0.10386653 0.09688494 0.07944696
#> AAO 0.10854097         NA 0.12294652 0.20901070
#> NAO 0.17671545 0.13116699         NA 0.08856063
#> PNA 0.07219261 0.09892819 0.09952883         NA
#> 
#> Dark causality matrix:
#>            AO       AAO       NAO       PNA
#> AO         NA 0.3836571 0.5111200 0.5083887
#> AAO 0.5000406        NA 0.4705213 0.4720415
#> NAO 0.4483534 0.4920280        NA 0.5345958
#> PNA 0.5551656 0.3840618 0.3810829        NA
```
