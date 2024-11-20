# Workshop 6: Generalized Linear Model

## 6.1 Issues with transforming data when assumptions of linear models are not met

- The response variable may change making interpretation difficult

- Linearity and homogeneity may not be simultaneously improved

- The boundaries of sample space may change
  
  
  
  

## 6.2 Nature of probability distributions

**Poisson Distribution:** 

- Skewed to the right when lambda is low

- Symmetrical when lambda is high
  
  

**Binomial Distribution:** 

- Predicts the probablity of observing a givern proportion of successes *p*, when the number of trials *n* is known

- The distribution is right skewed when p is small

- The distribution is skewed to the left when p is large

- The distribution is symmetrical when p ~ 0.5
  
  

> When the assumptions of the linear models are not met, distribution of the residuals (errors) needs to be switched to another probability distribution .
> 
> In those cases, the predicted values will have to be transformed by a **link function** 



**Link functions**

| Distribution of Y | Link function name | Code                        |
| ----------------- | ------------------ | --------------------------- |
| Normal            | Identity           | gaussian(link = "identity") |
| Bionomial         | Logit              | binomial(link = "logit")    |
| Poisson           | Log                | poisson(link = "log")       |
| Exponential       | Negative inverse   | Gamma(link = "inverse")     |

`glm()` function in R is used to run a generalized linear model

> Proportions are sometimes very similar to logistic regression



## 6.3 Goodness of fit and predictive power

- Pseudo-R<sup>2</sup> = (null deviance - residual deviance)/(null deviance)
  
  - Null deviance = deviance of the null mode
  
  - Residual deviance = deviance of the model of interest

- Can be calculated with the `PseudoR2()` function from the **DescTools** package
  
  
  
  

## 6.4 GLM with count data

- When there is no overdispersion _(mean = variance)_, Poisson GLM can be used

- Measure of overdispersion is phi
  
  - phi = residual deviance/residual degree of freedom
  
  - If phi > 1, data is overdispersed

- There are two ways of dealing with overdispersion
  
  - correct for it by using qausi-Poisson GLM
  
  - choose another distribution such as the negative binomial

- **Quasi-Poisson** 
  
  - adjusts the variance by using a _dispersion parameter_ 
  
  - these GLMs do not have AIC scores
  
  - affects model comparison
  
  - the overdispersion is not known in some cases

- **Negative binomial**
  
  - When the _dispersion parameter_ is > 15-20, negative binomial GLM should be used
  
  - It is a combination of poisson distribution and gamma distribution
  
  - can be modelled with the `glm.nb()` function from the MASS package





## 6.5 Other distribution

- When proportions do not arise from Bernoulli experiments, the use of  the `lm()` function is advised after running *logit transformation*

- If data appears normally distributed after _log transformation_,  a **log-normal distribution** in a GLM should be used

- **Gamma distribution** is like log-normal distribution, but more versatile


