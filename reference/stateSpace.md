# State Space Reconstruction

Reconstructs the state space of a time series using delay embedding,
creating a matrix where each row represents a point in the reconstructed
space.

## Usage

``` r
stateSpace(ts, E, tau, verbose = FALSE)
```

## Arguments

- ts:

  Numeric vector; time series data

- E:

  Integer; embedding dimension (E \> 1)

- tau:

  Integer; time delay (tau \> 0)

- verbose:

  Logical; whether to display progress information

## Value

An object of class "pc_state" containing:

- matrix: The reconstructed state space matrix

- parameters: List of reconstruction parameters

- original: Original time series data

## Details

State Space Reconstruction Analysis

The function implements Takens' embedding theorem to reconstruct state
space:

- Creates delay vectors using specified embedding dimension (E)

- Applies time delay (tau) between consecutive elements

- Handles boundary conditions and missing values

## Related Packages

- nonlinearTseries: Nonlinear time series analysis

- tseriesChaos: Chaos theory analysis tools

- fractal: Fractal analysis methods

## Examples

``` r
ts <- c(1:100)
result <- stateSpace(ts, E = 3, tau = 2)
plot(result)
#> Warning: no DISPLAY variable so Tk is not available

```
