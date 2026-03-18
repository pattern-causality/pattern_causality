# Calculate Full Details Pattern Causality Analysis

Implements an advanced pattern causality algorithm to explore the causal
relationships between two time series datasets. This function provides
comprehensive analysis of causality patterns, including state space
reconstruction, pattern identification, and causality strength
evaluation.

## Usage

``` r
pcFullDetails(
  X,
  Y,
  E,
  tau,
  h,
  weighted,
  metric = "euclidean",
  distance_fn = NULL,
  state_space_fn = NULL,
  relative = TRUE,
  verbose = FALSE
)
```

## Arguments

- X:

  Numeric vector; the first time series data

- Y:

  Numeric vector; the second time series data

- E:

  Integer; embedding dimension for state space reconstruction

- tau:

  Integer; time delay between data points

- h:

  Integer; prediction horizon for causality analysis

- weighted:

  Logical; whether to weight causality strength

- metric:

  Character; distance metric ('euclidean', 'manhattan', or 'maximum')

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

  Logical; if TRUE, prints computation progress (default: FALSE)

## Value

A pc_full_details object containing:

- backtest_time: Time points used for backtesting

- valid_time: Valid time points for analysis

- causality_real: Real causality spectrum

- causality_pred: Predicted causality spectrum

- state_spaces: State space reconstructions

- neighbors: Nearest neighbor information

- patterns: Pattern and signature information

- matrices: Causality matrices

- predictions: Predicted and actual values

- weighted: A logical indicating if weighted calculations were used

- E: Embedding dimension used for the analysis

## Details

Calculate Full Details Pattern Causality Analysis

The function implements these key steps:

- State Space Reconstruction: Creates shadow attractors using embedding

- Pattern Analysis: Converts time series into signature and pattern
  spaces

- Nearest Neighbor Analysis: Identifies and analyzes local dynamics

- Causality Evaluation: Computes predicted and actual causality matrices

- Results Validation: Provides detailed diagnostics and quality metrics
