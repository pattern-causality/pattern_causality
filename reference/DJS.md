# Dow Jones Stock Price Dataset

A comprehensive dataset containing daily stock prices for 29 companies
listed in the Dow Jones Industrial Average (DJIA). The dataset includes
opening, closing, high, and low prices for each stock.

## Usage

``` r
DJS
```

## Format

A data frame with daily stock prices for 29 companies.

## Source

Yahoo Finance

## Details

Dow Jones Stock Price Dataset

## Examples

``` r
data(DJS)
head(DJS)
#>         Date     X3M American.Express    Apple  Boeing Caterpillar
#> 1 2000-01-03 47.1875         45.88031 3.997768 40.1875    24.31250
#> 2 2000-01-04 45.3125         44.14794 3.660714 40.1250    24.00000
#> 3 2000-01-05 46.6250         42.96264 3.714286 42.6250    24.56250
#> 4 2000-01-06 50.3750         43.83794 3.392857 43.0625    25.81250
#> 5 2000-01-07 51.3750         44.47618 3.553571 44.3125    26.65625
#> 6 2000-01-10 51.1250         45.09618 3.491071 43.6875    25.78125
#>    Chevron Cisco.Systems Coca.Cola DowDuPont ExxonMobil
#> 1 41.81250      54.03125  28.18750  44.20833   39.15625
#> 2 41.81250      51.00000  28.21875  43.00000   38.40625
#> 3 42.56250      50.84375  28.46875  44.39583   40.50000
#> 4 44.37500      50.00000  28.50000  45.64583   42.59375
#> 5 45.15625      52.93750  30.37500  46.66667   42.46875
#> 6 43.93750      54.90625  29.40625  45.47917   41.87500
#>   General.Electric Goldman.Sachs      IBM    Intel Johnson...Johnson
#> 1         50.00000       88.3125 116.0000 43.50000          46.09375
#> 2         48.00000       82.7500 112.0625 41.46875          44.40625
#> 3         47.91667       78.8750 116.0000 41.81250          44.87500
#> 4         48.55727       82.2500 114.0000 39.37500          46.28125
#> 5         50.43750       82.5625 113.5000 41.00000          48.25000
#> 6         50.41667       84.3750 118.0000 42.87500          47.03125
#>   JPMorgan.Chase McDonald.s   Merck Microsoft     Nike  Pfizer
#> 1       48.58333    39.6250 67.6250  58.28125 6.015625 31.8750
#> 2       47.25000    38.8125 65.2500  56.31250 5.687500 30.6875
#> 3       46.95833    39.4375 67.8125  56.90625 6.015625 31.1875
#> 4       47.62500    38.8750 68.3750  55.00000 5.984375 32.3125
#> 5       48.50000    39.8750 74.9375  55.71875 5.984375 34.5000
#> 6       47.66667    40.0625 72.7500  56.12500 6.085938 34.4375
#>   Procter...Gamble The.Home.Depot Travelers United.Technologies
#> 1         53.59375        65.1875   33.0000            31.25000
#> 2         52.56250        61.7500   32.5625            29.96875
#> 3         51.56250        63.0000   32.3125            29.37500
#> 4         53.93750        60.0000   32.9375            30.78125
#> 5         58.25000        63.5000   34.2500            32.00000
#> 6         57.96875        63.1875   33.6250            32.31250
#>   UnitedHealth.Group  Verizon Walmart Walt.Disney
#> 1           6.718750 53.90316 66.8125    29.46252
#> 2           6.632813 52.16072 64.3125    31.18836
#> 3           6.617188 53.90316 63.0000    32.48274
#> 4           6.859375 53.28487 63.6875    31.18836
#> 5           7.664063 52.89142 68.5000    30.69527
#> 6           7.531250 52.61038 67.2500    35.37968
summary(DJS)
#>       Date                 X3M         American.Express
#>  Min.   :2000-01-03   Min.   : 39.50   Min.   :10.26   
#>  1st Qu.:2004-06-30   1st Qu.: 69.29   1st Qu.:40.33   
#>  Median :2008-12-18   Median : 81.63   Median :49.08   
#>  Mean   :2008-12-20   Mean   : 95.77   Mean   :52.91   
#>  3rd Qu.:2013-06-13   3rd Qu.:110.97   3rd Qu.:63.27   
#>  Max.   :2017-12-05   Max.   :243.14   Max.   :98.71   
#>      Apple              Boeing        Caterpillar        Chevron      
#>  Min.   :  0.9371   Min.   : 25.06   Min.   : 14.91   Min.   : 30.92  
#>  1st Qu.:  3.9358   1st Qu.: 49.98   1st Qu.: 37.00   1st Qu.: 47.45  
#>  Median : 23.1529   Median : 70.60   Median : 68.32   Median : 77.64  
#>  Mean   : 43.5477   Mean   : 82.62   Mean   : 63.83   Mean   : 77.79  
#>  3rd Qu.: 77.7789   3rd Qu.:103.71   3rd Qu.: 85.80   3rd Qu.:104.12  
#>  Max.   :176.2400   Max.   :277.97   Max.   :141.52   Max.   :134.85  
#>  Cisco.Systems     Coca.Cola       DowDuPont       ExxonMobil    
#>  Min.   : 8.60   Min.   :18.54   Min.   : 6.33   Min.   : 30.27  
#>  1st Qu.:18.47   1st Qu.:23.34   1st Qu.:31.22   1st Qu.: 45.27  
#>  Median :22.35   Median :28.05   Median :37.66   Median : 73.12  
#>  Mean   :24.50   Mean   :30.61   Mean   :38.70   Mean   : 68.41  
#>  3rd Qu.:27.09   3rd Qu.:38.79   3rd Qu.:45.51   3rd Qu.: 85.65  
#>  Max.   :80.06   Max.   :47.43   Max.   :73.32   Max.   :104.38  
#>  General.Electric Goldman.Sachs         IBM             Intel      
#>  Min.   : 6.66    Min.   : 52.00   Min.   : 55.07   Min.   :12.08  
#>  1st Qu.:22.53    1st Qu.: 97.18   1st Qu.: 92.35   1st Qu.:20.89  
#>  Median :28.85    Median :144.61   Median :119.16   Median :24.60  
#>  Mean   :29.15    Mean   :140.97   Mean   :128.20   Mean   :26.98  
#>  3rd Qu.:34.77    3rd Qu.:174.54   3rd Qu.:162.02   3rd Qu.:31.32  
#>  Max.   :60.00    Max.   :252.89   Max.   :215.80   Max.   :74.88  
#>  Johnson...Johnson JPMorgan.Chase     McDonald.s         Merck      
#>  Min.   : 34.25    Min.   : 15.45   Min.   : 12.38   Min.   :20.99  
#>  1st Qu.: 57.39    1st Qu.: 36.96   1st Qu.: 31.30   1st Qu.:36.20  
#>  Median : 63.79    Median : 43.03   Median : 57.98   Median :47.67  
#>  Mean   : 71.88    Mean   : 46.70   Mean   : 65.12   Mean   :48.40  
#>  3rd Qu.: 86.12    3rd Qu.: 53.56   3rd Qu.: 95.20   3rd Qu.:58.44  
#>  Max.   :143.62    Max.   :106.95   Max.   :172.99   Max.   :94.88  
#>    Microsoft          Nike            Pfizer      Procter...Gamble
#>  Min.   :15.15   Min.   : 3.320   Min.   :11.66   Min.   :26.81   
#>  1st Qu.:26.16   1st Qu.: 9.351   1st Qu.:22.57   1st Qu.:51.78   
#>  Median :28.83   Median :15.075   Median :29.00   Median :62.53   
#>  Mean   :33.91   Mean   :22.251   Mean   :28.50   Mean   :62.10   
#>  3rd Qu.:36.34   3rd Qu.:31.464   3rd Qu.:33.81   3rd Qu.:76.15   
#>  Max.   :84.88   Max.   :67.165   Max.   :49.00   Max.   :94.40   
#>  The.Home.Depot     Travelers      United.Technologies
#>  Min.   : 18.00   Min.   : 21.75   Min.   : 20.82     
#>  1st Qu.: 33.51   1st Qu.: 42.13   1st Qu.: 45.40     
#>  Median : 40.80   Median : 50.41   Median : 67.93     
#>  Mean   : 57.86   Mean   : 61.86   Mean   : 69.33     
#>  3rd Qu.: 75.09   3rd Qu.: 82.64   3rd Qu.: 92.31     
#>  Max.   :184.90   Max.   :136.36   Max.   :124.11     
#>  UnitedHealth.Group    Verizon         Walmart       Walt.Disney    
#>  Min.   :  5.953    Min.   :23.52   Min.   :42.27   Min.   : 13.58  
#>  1st Qu.: 25.835    1st Qu.:32.09   1st Qu.:50.43   1st Qu.: 25.68  
#>  Median : 47.490    Median :37.90   Median :55.00   Median : 33.73  
#>  Mean   : 57.130    Mean   :39.37   Mean   :59.10   Mean   : 46.83  
#>  3rd Qu.: 63.883    3rd Qu.:47.37   3rd Qu.:68.95   3rd Qu.: 63.61  
#>  Max.   :228.170    Max.   :58.62   Max.   :99.62   Max.   :121.69  
```
