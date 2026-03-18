# Pattern Causality Cross-Validation Analysis

Evaluates the robustness of pattern causality measures through repeated
sampling analysis. This function performs cross-validation by analyzing
multiple subsets of the data to assess the stability of causality
relationships.

## Usage

``` r
pcCrossValidation(
  X,
  Y,
  E,
  tau,
  metric = "euclidean",
  h,
  weighted,
  distance_fn = NULL,
  state_space_fn = NULL,
  numberset,
  random = TRUE,
  bootstrap = 1,
  verbose = FALSE,
  n_cores = 1,
  relative = TRUE
)
```

## Arguments

- X:

  Numeric vector representing the first time series.

- Y:

  Numeric vector representing the second time series.

- E:

  Integer specifying the embedding dimension.

- tau:

  Integer specifying the time delay.

- metric:

  Character string specifying the distance metric to use.

- h:

  Integer specifying the prediction horizon.

- weighted:

  Logical indicating whether to use weighted calculations.

- distance_fn:

  Optional custom distance function.

- state_space_fn:

  Optional custom state space function.

- numberset:

  Numeric vector of sample sizes to analyze.

- random:

  Logical indicating whether to use random sampling (default: TRUE).

- bootstrap:

  Integer specifying the number of bootstrap iterations (default: 1).

- verbose:

  Logical indicating whether to display progress messages.

- n_cores:

  Integer specifying the number of cores to use for parallel computation
  (default: 1).

- relative:

  Logical; if TRUE calculates relative changes ((new-old)/old), if FALSE
  calculates absolute changes (new-old) in signature space. Default is
  TRUE.

## Value

A pc_cv object containing:

- samples: Vector of sample sizes used

- results: Array of causality results

- parameters: List of analysis parameters

The results array structure depends on the bootstrap parameter:

- If bootstrap\>1: A three-dimensional array where first dimension
  represents sample sizes, second dimension contains statistics (mean,
  quantiles, median), and third dimension represents causality types
  (positive, negative, dark)

- If bootstrap=1: A three-dimensional array where first dimension
  represents sample sizes, second dimension contains single values, and
  third dimension represents causality types (positive, negative, dark)

## Details

Perform Pattern Causality Cross-Validation Analysis

The function implements these key steps:

- Validates input parameters and data

- Performs stratified sampling of time series data

- When random=TRUE and bootstrap\>1, performs bootstrap sampling

- Computes pattern causality measures for each sample

- Aggregates results across all samples

When bootstrap sampling is enabled (random=TRUE and bootstrap\>1), the
function returns statistics including mean, 5% quantile, 95% quantile,
and median for each sample size.

## See also

[`plot.pc_cv`](https://www.stavroglou.com/pattern_causality/reference/plot.pc_cv.md)
for visualizing cross-validation results
[`print.pc_cv`](https://www.stavroglou.com/pattern_causality/reference/print.pc_cv.md)
for printing cross-validation results
[`summary.pc_cv`](https://www.stavroglou.com/pattern_causality/reference/summary.pc_cv.md)
for summarizing cross-validation results

## Examples

``` r
# \donttest{
data(climate_indices)
X <- climate_indices$AO
Y <- climate_indices$AAO

# Basic cross-validation
cv_result <- pcCrossValidation(
  X, Y, 
  E = 3, tau = 1,
  metric = "euclidean",
  h = 1,
  weighted = FALSE,
  numberset = c(100, 200, 300)
)

# Cross-validation with bootstrap
cv_result_boot <- pcCrossValidation(
  X, Y,
  E = 3, tau = 1,
  metric = "euclidean",
  h = 1,
  weighted = FALSE,
  numberset = c(100, 200, 300),
  random = TRUE,
  bootstrap = 100
)
# }
```
