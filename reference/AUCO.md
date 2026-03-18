# Illapel Ecological Dataset

Raw rodent and rainfall data collected from the Las Chinchillas National
Reserve near Illapel, Coquimbo Region of Chile. This dataset provides
ecological time series for studying species interactions and
environmental effects.

## Usage

``` r
AUCO
```

## Format

A data frame with rodent and rainfall data.

## Source

Las Chinchillas National Reserve Research Station

## Details

Illapel Ecological Dataset

## Examples

``` r
data(AUCO)
head(AUCO)
#>   Date  PD AO     P    P1
#> 1 1987 367 60  57.5 513.4
#> 2 1988  87 21 104.3  57.5
#> 3 1989  47  1  63.4 104.3
#> 4 1990  59  1 200.8  63.4
#> 5 1991 150  1 307.2 200.8
#> 6 1992 121 49 162.5 307.2
summary(AUCO)
#>       Date            PD               AO           P         
#>  Min.   :1987   Min.   :  5.00   Min.   : 1   Min.   : 15.80  
#>  1st Qu.:1995   1st Qu.: 37.50   1st Qu.: 3   1st Qu.: 92.88  
#>  Median :2002   Median : 71.50   Median :12   Median :132.05  
#>  Mean   :2002   Mean   : 79.25   Mean   :18   Mean   :153.34  
#>  3rd Qu.:2010   3rd Qu.:101.25   3rd Qu.:21   3rd Qu.:198.25  
#>  Max.   :2018   Max.   :367.00   Max.   :98   Max.   :436.00  
#>        P1        
#>  Min.   : 15.80  
#>  1st Qu.: 95.35  
#>  Median :144.50  
#>  Mean   :168.76  
#>  3rd Qu.:201.82  
#>  Max.   :513.40  
```
