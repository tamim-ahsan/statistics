> This document notes the key points learned from this workshop

NB. _Function in R_ indicates this is a _base_ function

# 1. Linear Regression

## Workflow

1. Check if there is a linear relationship between the predictor(s) and the response - can be _visualized_

2. Fit the model first using the `lm()` function in R

3. Plot the model using the `plot()` function in R

4. Draw histogram of the residuals - use`hist()` function in R

5. Visualize the fitted line with `abline()` function in R

6. Check normality and skeness of the residuals using `shapiro.test()` and `skewness()` residuals can be accessed using the `residuals()` function in R

7. Look at the results using the `summary()` function in R or the `tbl_regression()` function from the **gtsummary** package

8. Access the coefficients using the `coef` function in R

9. If deviations are noticed, try _transforming_ the predictor(s) and/or the response variables
   
   
   
   

# 2. T-test

## Workflow

1. Look at the distribution of the data - visualize using boxplots

2. Check for the equality of the variances using the `var.test()` function in R

3. Two functions can be used
   
   - `t.test()` function in R
   - `lm()` followed by `anova()` function in R
     
     
     
     

# 3. Running ANOVA

## 3.1 Assumptions

1. Normal distribution

2. Homoscedasticity

3. Additivity 
   
   

## 3.2 Classification

1. One-way

2. Two-way

3. Repeated measures
   
   

## 3.3 Workflow

1. Visualize the groups using boxplots

2. Order the groups based on their _median_ using `tapply()` and `sort()` functions in R

3. Visualize the levels of particular factors using `plot.design()` funciton in R

4. Check for the homogeneity of variance using `bartlett.test()` funciton in R and `leveneTest()` function from the **car** package

5. ANOVA can be performed in two different ways
   
   - Using `aov()` function in R
   
   - Using `lm()` followed by `anova()` function in R

6. Do a post-hoc test using `TukeyHSD()` function in R
   
   

## 3.4 Contrasts

- User-defined contrasts can also be used

- The contrasts should display _pair-wise orthogonality_  

- To know more about orthogonal contrasts, visit the following resources
  
  - [University of New Hampshire]([Topic4_Reading](https://www.unh.edu/halelab/ANFS933/Readings/Topic4_Reading.pdf))
  
  - [UC Davis]([Microsoft Word - L4_Contrasts](https://psfaculty.plantsciences.ucdavis.edu/agr205/Lectures/2011_Lectures/L4_Contrasts.pdf))
    
    

## 3.5 Two-way ANOVA

- Check interaction (visuialize it) using the `interaction.plot()` function in R
  
  

## 3.6 Unbalanced ANOVA

- _Situation:_ Unequal smaple sizes across the groups

- _Solution_: Use the type III sum of squares using the `Anova()` function from the **car** package

- To know more about the types _sums of squares_, visit the following resource
  
  - [University of Toronto]([Types of Sums of Squares](https://utstat.utoronto.ca/reid/sta442f/2009/typeSS.pdf))
  
  - [University of Goettingen]([Anova – Type I/II/III SS explained](https://md.psych.bio.uni-goettingen.de/mv/unit/lm_cat/lm_cat_unbal_ss_explained.html))
    
    
    
    

# 4. ANCOVA

## 4.1 Assumptions

In addition to the general assumptions of linear models, the following assumptions are made

1. The same value range for all covariates

2. Variables that are fixed

3. No interaction between the categorical and continuous variables (not colinear)
   
   

## 4.2 Adjusted mean

- The adjusted means for the levels of a factor can be calculated and plotted using the `effect()` function from the **effects** function and the `plot()` function in R, respectively 
  
  
  
  

# 5. Multiple Linear Regression

## 5.1 Assumptions

Assumptions in addition to the usual assumptions for linear models

- Linear relationship between each explanatory variable and the response variable

- Independece of the predictors (no collinearity)
  
  

## 5. 2 Deviation from the assumptions

If linear relationship is not observed, polynomial regression can be used



## 5.3 Variation partitioning

_Issue_: Collinearity

_How to check:_ Perform variance inflation factor (VIF) analysis using the `vif()` function from the **car** package; VIF > 5 is indication of collinearity

_Solution:_ Variation partition analysis. The following functions from the **vegan** package are useful

- `varpart()`

- `rda()` 

 
