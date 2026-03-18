# Pattern Causality Effect Object

Creates a pattern causality effect object that contains information
about the received and exerted influences for different causality types.
This function constructs an object of class `pc_effect` to store the
results of effect analysis.

## Usage

``` r
pc_effect(positive = NULL, negative = NULL, dark = NULL, items = NULL)
```

## Arguments

- positive:

  Data frame containing positive causality effects.

- negative:

  Data frame containing negative causality effects.

- dark:

  Data frame containing dark causality effects.

- items:

  Names of items in the analysis.

## Value

An object of class "pc_effect".
