# Plot Pattern Causality Effect

Generates a plot to visualize the effects of positive, negative, or dark
causality. Displays the influence exerted versus influence received for
each item. This function generates a scatter plot showing the influence
exerted versus influence received for each item, colored by the
difference between exerted and received influence.

## Usage

``` r
# S3 method for class 'pc_effect'
plot(
  x,
  status = "positive",
  add_label = TRUE,
  point_size = 3,
  label_size = 3,
  ...
)
```

## Arguments

- x:

  A `pc_effect` object.

- status:

  Status of the effect to plot ("positive", "negative", or "dark").

- add_label:

  Logical, whether to add labels to the plot.

- point_size:

  Numeric value for point size (default: 3).

- label_size:

  Numeric value for label text size (default: 3).

- ...:

  Additional arguments passed to plotting functions.

## Value

Invisibly returns the ggplot object.

## Examples

``` r
# \donttest{
data(climate_indices)
dataset <- climate_indices[, -1]
pc_matrix_obj <- pcMatrix(dataset, E = 3, tau = 1, 
  metric = "euclidean", h = 1, weighted = TRUE, 
  verbose = FALSE)
effects <- pcEffect(pc_matrix_obj)
plot(effects, status = "positive")

# }
```
