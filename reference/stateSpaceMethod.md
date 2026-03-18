# State Space Reconstruction Interface

A generic interface for reconstructing state spaces from time series
data using either built-in or custom methods.

## Usage

``` r
stateSpaceMethod(x, E, tau, ...)

# Default S3 method
stateSpaceMethod(x, E, tau, ...)

# S3 method for class 'custom'
stateSpaceMethod(x, E, tau, method, ...)
```

## Arguments

- x:

  Input time series

- E:

  Embedding dimension (positive integer)

- tau:

  Time delay (positive integer)

- ...:

  Additional arguments passed to methods

- method:

  Custom function for state space reconstruction

## Value

A list containing the reconstructed state space components

## Details

Generic Interface for State Space Reconstruction

## Methods (by class)

- `stateSpaceMethod(default)`: Default state space reconstruction

- `stateSpaceMethod(custom)`: Custom state space reconstruction

## Examples

``` r
if (FALSE) { # \dontrun{
# Using default method
x <- rnorm(100)
s1 <- stateSpaceMethod(x, E=3, tau=2)

# Using custom method
custom_space <- function(x, E, tau) {
  list(matrix=embed(x, E))
}
s2 <- stateSpaceMethod(x, E=3, tau=2, method=custom_space)
} # }
```
