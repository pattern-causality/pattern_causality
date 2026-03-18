# Plot Pattern Causality Matrix

Creates a heatmap visualization of the pattern causality matrix for
positive, negative, or dark causality relationships. This function
generates a heatmap using `ggplot2` to visualize the specified causality
matrix.

## Usage

``` r
# S3 method for class 'pc_matrix'
plot(
  x,
  status,
  width = 0.85,
  height = 0.75,
  radius = grid::unit(3, "pt"),
  alpha = 0.53,
  show_text = FALSE,
  show_legend_title = FALSE,
  ...
)
```

## Arguments

- x:

  A `pc_matrix` object containing causality matrices.

- status:

  The type of causality to plot ("positive", "negative", or "dark").

- width:

  Numeric value specifying the width of the bars (default: 0.85).

- height:

  Numeric value specifying the height of the bars (default: 0.75).

- radius:

  Grid unit specifying the corner radius of the bars.

- alpha:

  Numeric value specifying the transparency (default: 0.53).

- show_text:

  Logical, whether to show numerical values on the plot.

- show_legend_title:

  Logical, whether to display the legend title.

- ...:

  Additional arguments passed to plotting functions.

## Value

A ggplot object invisibly.

## References

Stavroglou et al. (2020)
[doi:10.1073/pnas.1918269117](https://doi.org/10.1073/pnas.1918269117)

## Examples

``` r
data(climate_indices)
dataset <- climate_indices[, -1]
pc_matrix_obj <- pcMatrix(dataset, E = 3, tau = 1, 
  metric = "euclidean", h = 1, weighted = TRUE, 
  verbose = FALSE)
plot(pc_matrix_obj, status = "positive")
```
