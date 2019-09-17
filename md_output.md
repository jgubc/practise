# Exploration of Dataset **mtcars**

> This R Markdown document has been created to explore the dataset
> [mtcars](https://stat.ethz.ch/R-manual/R-devel/library/datasets/html/00Index.html)
> located in the R Datasets Package for [Assignment
> 1](https://stat545.stat.ubc.ca/evaluation/hw01/hw01/)

> #### **Description of dataset ‘mtcars’**
>
> ##### The datatset **‘mtcars’** is a dataset that contains 11 numeric variables with a total of 32 observations. Full description of the dataset can be found [here](https://stat.ethz.ch/R-manual/R-devel/library/datasets/html/mtcars.html).

##### **The variables are:-**

##### mpg - Miles/(US) gallon

##### cyl - Number of cylinders

##### disp - Displacement (cu.in.)

##### hp - Gross horsepower

##### drat - Rear axle ratio

##### wt - Weight (1000 lbs)

##### qsec - 1/4 mile time

##### vs - Engine (0 = V-shaped, 1 = straight)

##### am - Transmission (0 = automatic, 1 = manual)

##### gear - Number of forward gears

##### carb - Number of carburetors

> ##### The structure of the dataset can be seen below-

    ## 'data.frame':    32 obs. of  11 variables:
    ##  $ mpg : num  21 21 22.8 21.4 18.7 18.1 14.3 24.4 22.8 19.2 ...
    ##  $ cyl : num  6 6 4 6 8 6 8 4 4 6 ...
    ##  $ disp: num  160 160 108 258 360 ...
    ##  $ hp  : num  110 110 93 110 175 105 245 62 95 123 ...
    ##  $ drat: num  3.9 3.9 3.85 3.08 3.15 2.76 3.21 3.69 3.92 3.92 ...
    ##  $ wt  : num  2.62 2.88 2.32 3.21 3.44 ...
    ##  $ qsec: num  16.5 17 18.6 19.4 17 ...
    ##  $ vs  : num  0 0 1 1 0 1 0 1 1 1 ...
    ##  $ am  : num  1 1 1 0 0 0 0 0 0 0 ...
    ##  $ gear: num  4 4 4 3 3 3 3 4 4 4 ...
    ##  $ carb: num  4 4 1 1 2 1 4 2 2 4 ...

> ##### The variables **vs** (engine) and **am** (Transmission) are factor variables with two levels (0 and 1).

> #### **Checking for missing values-**
>
> ##### The ‘anyNA’ function is used to check if the dataset contains any missing values. As the ouput of the function is FALSE, it indicates all non-missing values in the dataset.

    ## [1] FALSE

> #### **Checking if variables are normally distributed-**
>
> ##### The variables **cyl, disp, drat, wt, qsec** are normally distributed. (Graphs in order of the variables listed).

![](md_output_files/figure-markdown_strict/unnamed-chunk-2-1.png)

> ##### The varibales **hp, mpg, gear** and **carb** are right skewed. (Graphs in order of the variables listed).

![](md_output_files/figure-markdown_strict/unnamed-chunk-3-1.png)

> #### **Scatterplots (to identify relationship between variables)-**
>
> ##### Below are the sample scatterplots of variables **wt vs mpg** and **wt vs disp**. The variables **wt** and **mpg** is negatively related as the points in the graph show a downhill pattern as we move from left to right while the variables **wt** and **disp** are positively related to each other as the data points for x increase as y values increase.

![](md_output_files/figure-markdown_strict/unnamed-chunk-4-1.png)

> #### **Linear Regression-**
>
> ##### Below is a simple linear regression to predict miles per gallon (**mpg**) travelled from weight (**wt**) of the car. The analysis is provided in the listing below and the resulting graph is shown.
>
> ##### The models fits moderately well as indicated by the **Adjusted R-squared value** of **0.74**. The plot shows the regression line fitted by the model. As the data values lie around this line, this indicates that the model fits the data well.

    ## 
    ## Call:
    ## lm(formula = mpg ~ wt, data = mtcars)
    ## 
    ## Residuals:
    ##     Min      1Q  Median      3Q     Max 
    ## -4.5432 -2.3647 -0.1252  1.4096  6.8727 
    ## 
    ## Coefficients:
    ##             Estimate Std. Error t value Pr(>|t|)    
    ## (Intercept)  37.2851     1.8776  19.858  < 2e-16 ***
    ## wt           -5.3445     0.5591  -9.559 1.29e-10 ***
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## Residual standard error: 3.046 on 30 degrees of freedom
    ## Multiple R-squared:  0.7528, Adjusted R-squared:  0.7446 
    ## F-statistic: 91.38 on 1 and 30 DF,  p-value: 1.294e-10

![](md_output_files/figure-markdown_strict/unnamed-chunk-5-1.png)
