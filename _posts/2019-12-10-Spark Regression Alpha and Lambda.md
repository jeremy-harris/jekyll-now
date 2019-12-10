---
layout: post
title: Spark Lasso Regression - Alpha & Lambda Changes
published: true
---
## Summary
When working on a project, using old notes, I tried to execute lasso linear regression on a spark dataset via the `ml_linear_regression` function from the `sparklyr` package. Formerly, you could set alpha and lambda inside of the command to utilize lasso regression, but this time I received an error code. After much searching and late night (drinking) reading of vignettes, I realized that the parameter names had changed.

## Old Way of Setting alpha & lambda
In short, when running regression on spark and specifically ridge and lasso regression, `alpha` and `lambda` no longer work as feature to set. In the past version you could include code that would allow you to set the alpha and lambda features so that the lasso regression could be modified to assist with model complexity reduction and feature selection.

```{r eval = FALSE}
ml_linear_regression(var1 ~ ., alpha = 0, lambda = 0.02)
```

Now however, there is an error code. 

**The error code provided was:**

Error: 2 components of `...` were not used. We detected these problematic arguments: * `alpha` * `lambda` Did you misspecify an argument?

## The New Way of Setting alpha & lambda
So, after reading the vignettes I finally just searched for alpha in the file and found the following: 

![vignette](/images/lasso-lambda_alpha.png)

I decided to just change the parameter names and re-ran the code. Magic!

```{r eval = FALSE}
ml_linear_regression(var1 ~ ., elastic_net_param = 1, reg_param = 0.02)
```

It works and all is well. Enjoy and I apologize for cutting into your late night reading/drinking time trying to figure this out. Maybe next time...
