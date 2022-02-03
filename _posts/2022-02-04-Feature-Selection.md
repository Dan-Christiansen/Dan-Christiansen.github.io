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
Strong correlation between variables may indicate dependent relationships between variables or redundancy. It is best to remove these or reduce the number of them to avoid overfitting

### Correlation metrics
Some useful measures of correlation are the *Pearson's correlation coefficient*, *Spearman's rank correlation coefficient*, and *Kendall's $\tau$ correlation coefficient* (not discussed here _yet_)

*Pearson's correlation coefficient* (linear) - Also called "correlation coefficient", describes the linear correlation between two variables. The correlation coefficient between variables $X$ and $Y$, $\rho$, is

<p style="text-align: center;">$$\rho_{X,Y}=cov(X,Y)/\sigma_X\sigma_Y$$</p>

* $$cov$$ is the covariance
* $$\sigma_X$$ is the standard deviation of $$X$$
* $$\sigma_Y$$ is the standard deviation of $$Y$$

$-1\le\rho\le+1$ - The larger the absolute value of $\rho$, the more strongly correlated the two variables are. $\rho=0$ indicates no correlation, i.e., no linear dependence between the variables

Calculate the Pearson's correlation coefficient in python with:
* [pandas.DataFrame.corr(method='pearson')](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.corr.html)
* [scipy.stats.pearsonr](https://docs.scipy.org/doc/scipy-0.15.1/reference/generated/scipy.stats.pearsonr.html)
* [sklearn.feature_selection.r_regression](https://scikit-learn.org/stable/modules/generated/sklearn.feature_selection.r_regression.html)

*Spearman's (rank) correlation coefficient* (nonlinear) - A measure of monotonicity between linear **or** nonlinear variable. It is the Pearson correlation coefficient between the rank variables. Spearman's correlation coefficient, $\rho_{R(X),R(Y)}$ or $r_s$, is calculated as

<p style="text-align: center;">$$\rho_{R(X),R(Y)}=r_s=cov(R(X),R(Y))/\sigma_{R(X)}\sigma_{R(Y)}$$</p>

* $\rho$ is the Pearson correlation coefficient applied to the rank variables
* $cov(R(X),R(Y))$ is the covariance of the rank variables
* $\sigma_{R(X)} and \sigma_{R(Y)}$ are the standard deviations of the rank variables

Calculate the Spearman's rank correlation coefficient in python with:
* [pandas.DataFrame.corr(method='spearman')](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.corr.html)
* [scipy.stats.spearmanr](https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.spearmanr.html)

Correlation strength is generally understood as
<p style="text-align: center;">
<b>STRONG</b>

$$0.7\le|\rho|\le1.0$$

<b>MODERATE</b>

$$0.3\le|\rho|<0.7$$

<b>WEAK</b>

$$0.0\le|\rho|<0.3$$
</p>

## Correlation plots
Correlation plots are a visual way to represent the correlation matrix, a table showing correlation coefficients between pairs of variables on the X and Y axes
