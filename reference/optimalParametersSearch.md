# Search for Optimal Parameters in Pattern Causality Analysis

Searches for the optimal embedding dimension (E) and time delay (tau) to
maximize the accuracy of causality predictions in a dataset. This
function implements a grid search approach to evaluate different
parameter combinations.

## Usage

``` r
optimalParametersSearch(
  Emax,
  tauMax,
  metric = "euclidean",
  distance_fn = NULL,
  state_space_fn = NULL,
  dataset,
  h = 0,
  weighted = FALSE,
  relative = TRUE,
  verbose = FALSE
)
```

## Arguments

- Emax:

  Positive integer \> 2; maximum embedding dimension to test

- tauMax:

  Positive integer; maximum time delay to test

- metric:

  Character string; distance metric for causality analysis ('euclidean',
  'manhattan', 'maximum'). Defaults to "euclidean". Ignored if
  `distance_fn` is provided.

- distance_fn:

  Optional custom distance function; takes two numeric vectors as input
  and returns a numeric distance. (default: NULL)

- state_space_fn:

  Optional custom function for state space reconstruction; takes a
  numeric vector and parameters E and tau as input and returns a
  reconstructed state space. (default: NULL)

- dataset:

  Numeric matrix; each column represents a time series.

- h:

  Positive integer; prediction horizon.

- weighted:

  Logical; if TRUE, weighted causality analysis is performed.

- relative:

  Logical; if TRUE calculates relative changes ((new-old)/old), if FALSE
  calculates absolute changes (new-old) in signature space. Default is
  TRUE.

- verbose:

  Logical; if TRUE, prints progress information. (default: FALSE)

## Value

A `pc_params` object containing:

- accuracy_summary: A data frame summarizing the accuracy for each
  parameter combination.

- computation_time: The time taken for the analysis.

- parameters: A list of the input parameters used.

## Details

Search for Optimal Parameters in Pattern Causality Analysis

This function evaluates each combination of embedding dimension and time
delay for their effectiveness in detecting different types of causality:

- Total causality: Overall causal relationship strength

- Positive causality: Direct positive influences

- Negative causality: Direct negative influences

- Dark causality: Complex or indirect causal relationships

## Examples

``` r
# \donttest{
data(climate_indices)
dataset <- climate_indices[, -1]
optimalParams <- optimalParametersSearch(
  Emax = 3, 
  tauMax = 3, 
  metric = "euclidean",
  dataset = dataset,
  h = 1,
  weighted = FALSE
)
print(optimalParams)
#> Pattern Causality Parameter Optimization Results
#> ---------------------------------------------
#> Computation time: 14.41919 secs 
#> 
#> Parameters tested:
#>   Emax: 3 
#>   tauMax: 3 
#>   Metric: euclidean 
#> 
#> First few values:
#>         E tau     Total  Positive   Negative        Dark
#> Combo 1 2   1 0.5975379 0.6496739 0.34926445 0.001061640
#> Combo 2 2   2 0.6243663 0.6783672 0.31961449 0.002018276
#> Combo 3 2   3 0.6232506 0.6801496 0.31855924 0.001291195
#> Combo 4 3   1 0.3461905 0.4235779 0.11284558 0.463576506
#> Combo 5 3   2 0.3808381 0.4415254 0.07647193 0.482002660
#> Combo 6 3   3 0.3873308 0.4358821 0.10169533 0.462422572
#> 
# }
```
