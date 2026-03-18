# Pattern Causality Cross-Validation Object

Creates a pattern causality cross-validation object containing results
from repeated sampling analysis. This function constructs an object of
class `pc_cv` to store the results of cross-validation analysis.

## Usage

``` r
pc_cv(samples = NULL, results = NULL, parameters = NULL)
```

## Arguments

- samples:

  Numeric vector of sample sizes used.

- results:

  Matrix containing causality results for each sample.

- parameters:

  List of analysis parameters.

## Value

An object of class "pc_cv".
