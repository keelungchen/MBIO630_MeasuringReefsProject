GroupProject_MeasuringReefs_Yan
================
Yan
2022-09-27

## Introduction

## Method

As the reference shown below:

<em><https://github.com/MBIO630-Remote-Sensing-2022/MBIO630_GroupProject_MeasuringReefs/blob/main/MBIO630_GroupProject_MeasuringReefs.md></em>

## Result

Effect of method. Two patch reefs show similar pattern of their method
differences.

<img src="MBIO630_GroupProject_MeasuringReefs_Yan_files/figure-gfm/data explore-1-1.png" style="display: block; margin: auto;" />

Effect of imagery resolution on area and perimeter

<img src="MBIO630_GroupProject_MeasuringReefs_Yan_files/figure-gfm/data explore-2-1.png" style="display: block; margin: auto;" />

Effect of date (i.e., do patch reefs measurably grow or shrink over
time?)

**We can not measure the growth of patch reefs in this data set** due to
low resolution and its overestimation in the recent years. If the data
is usable, these two patch reefs should show similar growth rate (slope
in the fig) because they grew in adjacent area.

<img src="MBIO630_GroupProject_MeasuringReefs_Yan_files/figure-gfm/data explore-3-1.png" style="display: block; margin: auto;" />

Now, let’s see if there’s anything going on with time when imagery
resolution is considered:

The result shows that **“Resolution” have more influence** in linear
regression model. Drop “year” can decrease AIC and have better model. In
addition, the **y \~ x1+x2** model is better than y \~ x1\*x2 model.

    ## 
    ## Call:
    ## lm(formula = area_m2 ~ imagery_resolution_m + year, data = data)
    ## 
    ## Residuals:
    ##     Min      1Q  Median      3Q     Max 
    ## -2851.2  -340.1   -55.8   281.3  7194.6 
    ## 
    ## Coefficients:
    ##                       Estimate Std. Error t value Pr(>|t|)    
    ## (Intercept)          9.274e+02  2.512e+04   0.037    0.971    
    ## imagery_resolution_m 9.373e+01  1.084e+01   8.644 8.71e-16 ***
    ## year                 1.321e-01  1.249e+01   0.011    0.992    
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## Residual standard error: 898.6 on 234 degrees of freedom
    ##   (53 observations deleted due to missingness)
    ## Multiple R-squared:  0.2745, Adjusted R-squared:  0.2683 
    ## F-statistic: 44.27 on 2 and 234 DF,  p-value: < 2.2e-16
    ## 
    ## Single term deletions
    ## 
    ## Model:
    ## area_m2 ~ imagery_resolution_m + year
    ##                      Df Sum of Sq       RSS    AIC F value    Pr(>F)    
    ## <none>                            188949488 3226.6                      
    ## imagery_resolution_m  1  60328126 249277614 3290.2 74.7119 8.707e-16 ***
    ## year                  1        90 188949578 3224.6  0.0001    0.9916    
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

Or reef identity (reef number):

The result shows that **both “reef ID” and “resolution” should not be
dropped**.

    ## 
    ## Call:
    ## lm(formula = area_m2 ~ imagery_resolution_m + reef_no, data = data)
    ## 
    ## Residuals:
    ##     Min      1Q  Median      3Q     Max 
    ## -2519.9  -223.8   -22.0   223.9  6951.0 
    ## 
    ## Coefficients:
    ##                      Estimate Std. Error t value Pr(>|t|)    
    ## (Intercept)          8185.298   1142.848   7.162 1.02e-11 ***
    ## imagery_resolution_m   90.543      9.266   9.772  < 2e-16 ***
    ## reef_no              -332.590     54.277  -6.128 3.75e-09 ***
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## Residual standard error: 834.2 on 234 degrees of freedom
    ##   (53 observations deleted due to missingness)
    ## Multiple R-squared:  0.3748, Adjusted R-squared:  0.3695 
    ## F-statistic: 70.15 on 2 and 234 DF,  p-value: < 2.2e-16
    ## 
    ## Single term deletions
    ## 
    ## Model:
    ## area_m2 ~ imagery_resolution_m + reef_no
    ##                      Df Sum of Sq       RSS    AIC F value    Pr(>F)    
    ## <none>                            162822660 3191.3                      
    ## imagery_resolution_m  1  66441672 229264332 3270.4  95.486 < 2.2e-16 ***
    ## reef_no               1  26126918 188949578 3224.6  37.548 3.749e-09 ***
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

Analyze the trade-offs between the different imagery

<img src="MBIO630_GroupProject_MeasuringReefs_Yan_files/figure-gfm/data analysis-3-1.png" style="display: block; margin: auto;" />

Analyze the difference between observers. We can find that there are
**three outliers** in patch reef \#20. Apart from that, the
**measurement between different observers is consistent**.

<img src="MBIO630_GroupProject_MeasuringReefs_Yan_files/figure-gfm/data analysis-4-1.png" style="display: block; margin: auto;" />

## Discussion

#### 1.Which method did you find to be more variable among groups/individuals - field or imagery?

-   Imagery is more variable than field among groups.
-   The reason might be due to the multiple data sources of imagery,
    such as aerial and satellites. The resolution of images, filming
    angle (nadir or tilted) and quality of images (weather, sunshine
    intensity or quality of optical sensors) among multiple data sources
    might cause uncertainty of measurement and increase its variability.

#### 2.How did imagery resolution affect your measurements?

Lower imagery resolution tend to overestimate patch reef area. Moreover,
larger patch reef (#20) tend to be overestimated more obviously. Surface
area would have more overestimation than perimeter. Or these might be
just due to the outliers in \#20. We need more data across different
size of reefs to make sure whether larger size would have more
overestimation.

#### 3.What are the trade-offs between field vs imagery measurements?

| Measurements | pros                                                                                                                           | cons                                                                                                          |
|:-------------|:-------------------------------------------------------------------------------------------------------------------------------|:--------------------------------------------------------------------------------------------------------------|
| Field        | lower variability, can be more precise and accurate, can get the data whenever we want                                         | time-consumed, investment of our own measuring equipment (such as handheld GPS and boat) is needed            |
| Imagery      | free data resources are available, measurement can be verified by different people and multiple times, can be measured rapidly | higher variability, need extra cost to get higher quality data, desired data at certain time might be limited |

#### 4.What are the trade-offs between the different imagery a) platforms and b) resolutions?

| a\) Platforms  | pros                                                                                              | cons                                                                                                                                |
|:---------------|:--------------------------------------------------------------------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------|
| Google Earth   | free, have higher resolution, can save the measurement results and study sites,                   | database of images is smaller, no filter for searching images, Graphical User Interface is out-of-date                              |
| Planet Exlorer | database of images is larger, have filter for searching images, Graphical User Interface is fancy | registration is needed to access data and might be rejected, the measurement tools is inconvenient, many images have low resolution |

| b\) Resolution | pros                                                                               | cons                                                                             |
|:---------------|:-----------------------------------------------------------------------------------|:---------------------------------------------------------------------------------|
| High           | measurement can be more precise and accurate, can measure smaller research targets | data might be expensive or limited, larger storage space is needed               |
| Low            | data is easy to access, can be shown smoothly in computer                          | measurement might have high variability, cannot measure smaller research targets |

#### 5.How should we measure the growth rate of reefs in imagery?

The resolution of data should keep consistent. Or the variation that is
caused by resolution should be smaller than growth rate.
