# Plot Pattern Causality Components

Visualizes the positive, negative, and dark causality components as a
barplot. This function takes a `pc_fit` object and generates a barplot
showing the strength of each causality component.

## Usage

``` r
plot_components(x, ...)
```

## Arguments

- x:

  An object containing pattern causality results, typically a `pc_fit`
  object.

- ...:

  Additional arguments passed to the underlying plotting functions.

## Value

NULL invisibly.

## Examples

``` r
data(climate_indices)
X <- climate_indices$AO
Y <- climate_indices$AAO
pc_result <- pcLightweight(X, Y, E = 3, tau = 2, metric = "euclidean", h = 1, weighted = TRUE)
plot_components(pc_result)
```
