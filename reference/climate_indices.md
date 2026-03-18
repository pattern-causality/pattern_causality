# Climate Indices Dataset

A comprehensive time series dataset containing various climate indices
used for pattern causality analysis. This dataset includes multiple
climate indicators measured over time.

## Usage

``` r
climate_indices
```

## Format

A data frame with 100 rows and 5 columns:

- Date:

  Date; Date of the measurement

- AO:

  Numeric; Arctic Oscillation index

- AAO:

  Numeric; Antarctic Oscillation index

- NAO:

  Numeric; North Atlantic Oscillation index

- PNA:

  Numeric; Pacific/North American index

## Source

<https://www.cpc.ncep.noaa.gov/>

## Details

Climate Indices Dataset

## Examples

``` r
data(climate_indices)
head(climate_indices)
#>         Date      AO    AAO   NAO   PNA
#> 1 1979-01-01 -2.2328 0.2088 -1.38 -0.69
#> 2 1979-02-01 -0.6967 0.3563 -0.67 -1.82
#> 3 1979-03-01 -0.8141 0.8992  0.78  0.38
#> 4 1979-04-01 -1.1568 0.6776 -1.71  0.09
#> 5 1979-05-01 -0.2501 0.7237 -1.03  1.35
#> 6 1979-06-01  0.9332 1.7000  1.60 -1.64
summary(climate_indices)
#>       Date                  AO                AAO         
#>  Min.   :1979-01-01   Min.   :-4.26570   Min.   :-3.0097  
#>  1st Qu.:1990-02-15   1st Qu.:-0.53485   1st Qu.:-0.5412  
#>  Median :2001-04-01   Median :-0.00830   Median : 0.1494  
#>  Mean   :2001-04-01   Mean   : 0.01632   Mean   : 0.1077  
#>  3rd Qu.:2012-05-16   3rd Qu.: 0.61135   3rd Qu.: 0.7763  
#>  Max.   :2023-07-01   Max.   : 3.49530   Max.   : 2.6906  
#>       NAO                PNA         
#>  Min.   :-3.18000   Min.   :-3.0700  
#>  1st Qu.:-0.67000   1st Qu.:-0.5200  
#>  Median : 0.13000   Median : 0.2093  
#>  Mean   : 0.06711   Mean   : 0.1321  
#>  3rd Qu.: 0.85500   3rd Qu.: 0.7946  
#>  Max.   : 2.63000   Max.   : 2.6600  
```
