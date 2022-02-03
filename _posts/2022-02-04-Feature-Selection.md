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

## Checking correlation to determine redundant redundant variables
Strong correlation between variables may indicate dependent relationships between variables or redundancy. It is best to remove these or reduce the number of them to avoid overfitting.

### Correlation metrics
Two useful measures of correlation are the *Pearson's correlation coefficient* and *Spearman's rank correlation coefficient*

*Pearson's correlation coefficient* (linear) - Also called "correlation coefficient", describes the linear correlation between two variables. The correlation coefficient between variables $X$ and $Y$, $\rho$, is

<p style="text-align: center;">$$\rho_{X,Y}=cov(X,Y)/\sigma_X\sigma_Y$$</p>

* $$cov$$ is the covariance
* $$\sigma_X$$ is the standard deviation of $$X$$
* $$\sigma_Y$$ is the standard deviation of $$Y$$

$-1\le\rho\le+1$ - The larger the absolute value of $\rho$, the more strongly correlated the two variables are. $\rho=0$ indicates no correlation, i.e., no linear dependence between the variables

*Spearman's (rank) correlation coefficient* (nonlinear) - A measure of monotonicity between linear **or** nonlinear variable. It is the Pearson correlation coefficient between the rank variables. Spearman's correlation coefficient, $\rho_{R(X),R(Y)}$ or $r_s$, is calculated as

<p style="text-align: center;">$$\rho_{R(X),R(Y)}=r_s=cov(R(X),R(Y))/\sigma_{R(X)}\sigma_{R(Y)}$$</p>

* $\rho$ is the Pearson correlation coefficient applied to the rank variables
* $cov(R(X),R(Y))$ is the covariance of the rank variables
* $\sigma_{R(X)} and \sigma_{R(Y)}$ are the standard deviations of the rank variables

## Correlation plots
Correlation plots are a visual way to represent the correlation matrix, a table showing correlation coefficients between pairs of variables on the X and Y axes
