---
title: 'Feature selection techniques'
date: 2022-02-04
permalink: /posts/2022/02/Feature-Selection/
tags:
  - tutorials
  - feature selection
  - descriptor selection
---

## Some references
[Machine Learning Mastery](https://machinelearningmastery.com/feature-selection-with-real-and-categorical-data/)

## General notes
*Supervised* feature selection techniques consider the target variable when determining variable relevance
* Wrapper - Evaluate performance of model trained on subsets of input features and select features with greatest performance
* Filter - Feature selection based on relationship between feature and target variables
* Intrinsic - Automatically perform feature selection during training (e.g., Decision trees, LASSO)

*Unsupervised* feature selection techniques ignore the target variable and remove redundant variables (e.g., by using correlation)

## Checking collinearity with pair plots
*Pearson's correlation coefficient* (linear) - Also called "correlation coefficient". Describe the correlation between two variables. The correlation coefficient between variables $X$ and $Y$, $\rho$, is

<p style="text-align: center;">$$\rho_{X,Y}=cov(X,Y)/\sigma_X\sigma_Y$$</p>

* $$cov$$ is the covariance
* $$\sigma_X$$ is the standard deviation of $$X$$
* $$\sigma_Y$$ is the standard deviation of $$Y$$

$-1\le\rho\le+1$ - The larger the absolute value of $\rho$, the more strongly correlated the two variables are. $\rho=0$ indicates no correlation, i.e., no linear dependence between the variables

*Spearman's rank coefficient* (nonlinear) -
