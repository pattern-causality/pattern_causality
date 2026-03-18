# Unveiling Causal Relationships in Time Series Data

This vignette demonstrates advanced techniques for examining causal
relationships between time series using the `patterncausality` package.
We will focus on three key aspects:

1.  **Cross-validation methods:** To rigorously assess the robustness of
    our findings, ensuring they are not mere artifacts of the data.
2.  **Parameter optimization:** To fine-tune our analysis for the most
    accurate and reliable results.
3.  **Visualization of causality relationships:** To provide clear and
    intuitive insights into the causal connections between time series.

Through cross-validation, we aim to understand:

- **Reliability of results:** How dependable are our conclusions?
- **Robustness across different sample sizes:** Do our findings hold
  true regardless of the amount of data used?
- **Stability of causality patterns:** Are the identified causal
  relationships consistent over time and across different data subsets?

## Cross-Validation: Ensuring the Reliability of Causal Inference

To demonstrate the application of cross-validation, we will begin by
importing a climate dataset from the `patterncausality` package.

``` r
library(patterncausality)
data(climate_indices)
```

Now, let’s apply cross-validation to evaluate the robustness of pattern
causality. We will use the Pacific North American (PNA) and North
Atlantic Oscillation (NAO) climate indices as our example time series.

``` r
set.seed(123)
X <- climate_indices$PNA
Y <- climate_indices$NAO
result <- pcCrossValidation(
  X = X, 
  Y = Y,  
  numberset = seq(100, 500, by = 10),
  E = 3,
  tau = 2,
  metric = "euclidean",
  h = 1,
  weighted = FALSE
)
print(result$results)
#> , , positive
#> 
#>         value
#> 100 0.5161290
#> 110 0.5555556
#> 120 0.2826087
#> 130 0.4482759
#> 140 0.4807692
#> 150 0.3461538
#> 160 0.4736842
#> 170 0.2608696
#> 180 0.3777778
#> 190 0.3815789
#> 200 0.5270270
#> 210 0.3823529
#> 220 0.3815789
#> 230 0.4375000
#> 240 0.4375000
#> 250 0.3707865
#> 260 0.4705882
#> 270 0.4152542
#> 280 0.4259259
#> 290 0.4421053
#> 300 0.4833333
#> 310 0.4111111
#> 320 0.4778761
#> 330 0.4047619
#> 340 0.4094488
#> 350 0.4428571
#> 360 0.3760000
#> 370 0.3925926
#> 380 0.4295775
#> 390 0.4600000
#> 400 0.4424242
#> 410 0.3767123
#> 420 0.3774834
#> 430 0.4352941
#> 440 0.4578313
#> 450 0.4494382
#> 460 0.4245810
#> 470 0.4321608
#> 480 0.4350000
#> 490 0.4421053
#> 500 0.4326923
#> 
#> , , negative
#> 
#>          value
#> 100 0.06451613
#> 110 0.00000000
#> 120 0.08695652
#> 130 0.00000000
#> 140 0.03846154
#> 150 0.07692308
#> 160 0.05263158
#> 170 0.08695652
#> 180 0.06666667
#> 190 0.05263158
#> 200 0.05405405
#> 210 0.01470588
#> 220 0.03947368
#> 230 0.07812500
#> 240 0.04687500
#> 250 0.05617978
#> 260 0.06862745
#> 270 0.02542373
#> 280 0.03703704
#> 290 0.07368421
#> 300 0.06666667
#> 310 0.06666667
#> 320 0.07079646
#> 330 0.03174603
#> 340 0.03149606
#> 350 0.03571429
#> 360 0.08000000
#> 370 0.08148148
#> 380 0.02816901
#> 390 0.07333333
#> 400 0.04242424
#> 410 0.08219178
#> 420 0.08609272
#> 430 0.04705882
#> 440 0.04819277
#> 450 0.03932584
#> 460 0.03351955
#> 470 0.04522613
#> 480 0.04500000
#> 490 0.04736842
#> 500 0.04807692
#> 
#> , , dark
#> 
#>         value
#> 100 0.4193548
#> 110 0.4444444
#> 120 0.6304348
#> 130 0.5517241
#> 140 0.4807692
#> 150 0.5769231
#> 160 0.4736842
#> 170 0.6521739
#> 180 0.5555556
#> 190 0.5657895
#> 200 0.4189189
#> 210 0.6029412
#> 220 0.5789474
#> 230 0.4843750
#> 240 0.5156250
#> 250 0.5730337
#> 260 0.4607843
#> 270 0.5593220
#> 280 0.5370370
#> 290 0.4842105
#> 300 0.4500000
#> 310 0.5222222
#> 320 0.4513274
#> 330 0.5634921
#> 340 0.5590551
#> 350 0.5214286
#> 360 0.5440000
#> 370 0.5259259
#> 380 0.5422535
#> 390 0.4666667
#> 400 0.5151515
#> 410 0.5410959
#> 420 0.5364238
#> 430 0.5176471
#> 440 0.4939759
#> 450 0.5112360
#> 460 0.5418994
#> 470 0.5226131
#> 480 0.5200000
#> 490 0.5105263
#> 500 0.5192308
```

To better visualize the results, we will use the `plot` function to
generate a line chart.

``` r
plot(result)
```

![](series_files/figure-html/unnamed-chunk-4-1.png)

As you can see from the plot, the location of the causality tends to
stabilize as the sample size increases. This indicates that our method
is effective at capturing the underlying patterns and causal connections
within the time series.

In this tutorial, you’ve learned how to use cross-validation to assess
the reliability of time series causality and how to use visualization
tools to better understand the results.

## Cross-Validation: Convergence of Pattern Causality

Now, let’s examine the cross-validation process when the `random`
parameter is set to `FALSE`. This approach uses a systematic sampling
method rather than random sampling.

``` r
set.seed(123)
X <- climate_indices$PNA
Y <- climate_indices$NAO
result_non_random <- pcCrossValidation(
  X = X,
  Y = Y,
  numberset = seq(100, 500, by = 100),
  E = 3,
  tau = 2,
  metric = "euclidean",
  h = 1,
  weighted = FALSE,
  random = FALSE
)
print(result_non_random$results)
#> , , positive
#> 
#>         value
#> 100 0.3170732
#> 200 0.3750000
#> 300 0.4201681
#> 400 0.4250000
#> 500 0.4438776
#> 
#> , , negative
#> 
#>          value
#> 100 0.07317073
#> 200 0.05000000
#> 300 0.03361345
#> 400 0.05000000
#> 500 0.04591837
#> 
#> , , dark
#> 
#>         value
#> 100 0.6097561
#> 200 0.5750000
#> 300 0.5462185
#> 400 0.5250000
#> 500 0.5102041
```

We can also visualize the results of the non-random cross-validation:

``` r
plot(result_non_random)
```

![](series_files/figure-html/unnamed-chunk-6-1.png)

By comparing the results of the random and non-random cross-validation,
you can gain a deeper understanding of how different sampling methods
affect the stability and reliability of the causality analysis.

## Cross-Validation with Bootstrap Analysis

To obtain more robust results and understand the uncertainty in our
causality measures, we can use bootstrap sampling in our
cross-validation analysis. This approach repeatedly samples the data
with replacement and provides statistical summaries of the causality
measures.

``` r
set.seed(123)
X <- climate_indices$PNA
Y <- climate_indices$NAO
result_boot <- pcCrossValidation(
  X = X,
  Y = Y,
  numberset = seq(100, 500, by = 100),
  E = 3,
  tau = 2,
  metric = "euclidean",
  h = 1,
  weighted = FALSE,
  random = TRUE,
  bootstrap = 10  # Perform 100 bootstrap iterations
)
```

The bootstrap analysis provides several statistical measures for each
sample size: - Mean: Average causality measure across bootstrap
samples - 5% and 95% quantiles: Confidence intervals for the causality
measure - Median: Central tendency measure robust to outliers

Let’s examine the results:

``` r
print(result_boot$results)
#> , , positive
#> 
#>          mean        5%       95%    median
#> 100 0.3889626 0.1658565 0.5385366 0.4400000
#> 200 0.4357484 0.3181034 0.5407240 0.4564051
#> 300 0.4832521 0.3560374 0.5663069 0.5061667
#> 400 0.4518897 0.3991413 0.5327971 0.4397759
#> 500 0.4819909 0.4055643 0.5759262 0.4609731
#> 
#> , , negative
#> 
#>           mean         5%       95%     median
#> 100 0.07405050 0.00000000 0.2208333 0.06125000
#> 200 0.09223979 0.02742640 0.1688200 0.09397766
#> 300 0.07018415 0.03477557 0.1155612 0.06142473
#> 400 0.08727687 0.04740125 0.1175632 0.09693044
#> 500 0.07939358 0.05032955 0.1151048 0.07826748
#> 
#> , , dark
#> 
#>          mean        5%       95%    median
#> 100 0.5369869 0.4285366 0.7468750 0.5000000
#> 200 0.4720118 0.3688060 0.5974138 0.4659991
#> 300 0.4465638 0.3791379 0.5349490 0.4265903
#> 400 0.4608335 0.3995160 0.5092123 0.4737526
#> 500 0.4386155 0.3534418 0.4904713 0.4573483
```

We can visualize the bootstrap results using the plot function, which
now shows confidence intervals:

``` r
plot(result_boot, separate = TRUE)
```

![](series_files/figure-html/unnamed-chunk-9-1.png)

The shaded area in the plot represents the range between the 5th and
95th percentiles of the bootstrap samples, providing a measure of
uncertainty in our causality estimates. The solid line shows the median
value, which is more robust to outliers than the mean.
