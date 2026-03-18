# Calculate Pattern Causality Accuracy

Evaluates the causality prediction accuracy across multiple time series
within a dataset using the PC Mk. II Light method. This function
analyzes pairwise causality relationships and computes different types
of causality measures.

## Usage

``` r
pcAccuracy(
  dataset,
  E,
  tau,
  metric = "euclidean",
  h,
  weighted,
  distance_fn = NULL,
  state_space_fn = NULL,
  relative = TRUE,
  verbose = FALSE
)
```

## Arguments

- dataset:

  A matrix or data frame where each column represents a time series

- E:

  Integer; embedding dimension for state space reconstruction (E \> 1)

- tau:

  Integer; time delay for state space reconstruction (tau \> 0)

- metric:

  Character; distance metric to use, one of "euclidean", "manhattan", or
  "maximum"

- h:

  Integer; prediction horizon, indicating forecast distance (h \>= 0)

- weighted:

  Logical; whether to use weighted approach in calculating causality
  strengths

- distance_fn:

  Optional custom distance function for computing distances (default:
  NULL)

- state_space_fn:

  Optional custom function for state space reconstruction (default:
  NULL)

- relative:

  Logical; if TRUE calculates relative changes ((new-old)/old), if FALSE
  calculates absolute changes (new-old) in signature space. Default is
  TRUE.

- verbose:

  Logical; whether to display progress information (default: FALSE)

## Value

An object of class "pc_accuracy" containing:

- parameters: List of input parameters (E, tau, metric, h, weighted)

- total: Mean total causality across all pairs

- positive: Mean positive causality across all pairs

- negative: Mean negative causality across all pairs

- dark: Mean dark causality across all pairs

- matrices: Raw causality matrices for each type

## Details

Calculate Pattern Causality Accuracy

## See also

[`pcMatrix`](https://www.stavroglou.com/pattern_causality/reference/pcMatrix.md)
for analyzing individual causality matrices
[`pcLightweight`](https://www.stavroglou.com/pattern_causality/reference/pcLightweight.md)
for pairwise causality analysis

## Examples

``` r
# \donttest{
data(climate_indices)
data <- climate_indices[, -1]
results <- pcAccuracy(dataset = data, E = 3, tau = 1, 
                     metric = "euclidean", h = 1, 
                     weighted = TRUE, verbose = TRUE)
#> Analyzing causality relationships...
#> Analyzing relationships: 2/12 (17%)Analyzing relationships: 3/12 (25%)Analyzing relationships: 4/12 (33%)Analyzing relationships: 4/12 (33%)Analyzing relationships: 6/12 (50%)Analyzing relationships: 7/12 (58%)Analyzing relationships: 7/12 (58%)Analyzing relationships: 8/12 (67%)Analyzing relationships: 10/12 (83%)Analyzing relationships: 10/12 (83%)Analyzing relationships: 11/12 (92%)Analyzing relationships: 12/12 (100%)
#> 
#> Computing summary statistics...
print(results)
#> Pattern Causality Accuracy Analysis
#> ----------------------------------
#> Parameters:
#>   E: 3 
#>   tau: 1 
#>   metric: euclidean 
#>   h: 1 
#> 
#> Causality measures:
#>   Total: 0.3459 
#>   Positive: 0.4143 
#>   Negative: 0.1156 
#>   Dark: 0.4701 
#> 
# }
```
