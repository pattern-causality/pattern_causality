# Plot Total Pattern Causality

Visualizes the total pattern causality strength as a barplot. This
function takes a `pc_fit` object and generates a barplot showing the
overall causality strength.

## Usage

``` r
plot_total(x, ...)
```

## Arguments

- x:

  An object containing pattern causality results, typically a `pc_fit`
  object.

- ...:

  Additional arguments passed to the underlying plotting functions.

## Value

NULL invisibly.

## References

Stavroglou et al. (2020)
[doi:10.1073/pnas.1918269117](https://doi.org/10.1073/pnas.1918269117)

## See also

[`plot_components`](https://www.stavroglou.com/pattern_causality/reference/plot_components.md)
for visualizing individual causality components.

## Examples

``` r
data(climate_indices)
X <- climate_indices$AO
Y <- climate_indices$AAO
pc_result <- pcLightweight(X, Y, E = 3, tau = 2, metric = "euclidean", h = 1, weighted = TRUE)
plot_total(pc_result)
```
