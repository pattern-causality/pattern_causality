# Cross Pattern Causality Matrix Analysis

Analyzes pattern causality relationships between multiple time series in
X and multiple time series in Y by computing pairwise causality measures
and organizing them into a matrix.

## Usage

``` r
pcCrossMatrix(
  X,
  Y,
  E,
  tau,
  metric = "euclidean",
  h,
  weighted = TRUE,
  distance_fn = NULL,
  state_space_fn = NULL,
  relative = TRUE,
  verbose = FALSE,
  n_cores = 1
)
```

## Arguments

- X:

  Matrix or data frame of time series for the cause

- Y:

  Matrix or data frame of time series for the effect

- E:

  Integer; embedding dimension

- tau:

  Integer; time delay

- metric:

  Character; distance metric ("euclidean", "manhattan", "maximum")

- h:

  Integer; prediction horizon

- weighted:

  Logical; whether to use weighted causality

- distance_fn:

  Optional custom distance function

- state_space_fn:

  Optional custom state space reconstruction function

- relative:

  Logical; if TRUE calculates relative changes ((new-old)/old), if FALSE
  calculates absolute changes (new-old) in signature space. Default is
  TRUE.

- verbose:

  Logical; whether to print progress

- n_cores:

  Integer; number of cores for parallel computation

## Value

A pc_matrix object containing causality matrices

## Details

Compute Cross Pattern Causality Matrix Analysis

The function performs these key steps:

- Validates input data and parameters

- Computes pairwise causality measures between X and Y

- Organizes results into a causality matrix

- Provides summary statistics for each causality type

## Related Packages

- vars: Vector autoregression analysis

- tseries: Time series analysis tools

- forecast: Time series forecasting methods
