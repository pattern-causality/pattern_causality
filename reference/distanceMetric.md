# Distance Metric Interface

A generic interface for computing distances between observations using
either built-in or custom distance metrics.

## Usage

``` r
distanceMetric(x, method = "euclidean", ...)

# Default S3 method
distanceMetric(x, method = "euclidean", ...)

# S3 method for class 'custom'
distanceMetric(x, method, ...)
```

## Arguments

- x:

  Input data matrix or vector

- method:

  Custom function to compute distances

- ...:

  Additional arguments passed to methods

## Value

A distance object or matrix containing pairwise distances

## Details

Generic Interface for Distance Metrics

## Methods (by class)

- `distanceMetric(default)`: Default method using stats::dist

- `distanceMetric(custom)`: Custom distance metric implementation

## Examples

``` r
if (FALSE) { # \dontrun{
# Using default method
x <- matrix(rnorm(100), ncol=2)
d1 <- distanceMetric(x, "euclidean")

# Using custom method
custom_dist <- function(x) as.dist(crossprod(x))
d2 <- distanceMetric(x, method=custom_dist)
} # }
```
