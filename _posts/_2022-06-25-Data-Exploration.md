---
title: 'Data Exploration'
date: 2022-06-25
permalink: /posts/2022/06/DataExploration/
tags:
  - research
  - data
  - python
  - data science
  - data analytics
  - tutorials
---

Tools and best practices for visualizing and interpreting data. This is far from exhaustive, primarily covering tools I regularly use. This post is written for the python programming language; there are equivalent functions in Excel, Matlab, R, etc.

## Data Exploration

When dealing with data, it is quite often easy to jump straight into number crunching and retrieving model predictions and scores. However, without examining the data beforehand, it is possible (and likely) to miss patterns, anomalies, and necessary treatments which should be understood before any transformations or useage is applied. For this reason, data exploration is the first step of data analysis. In this step, data visualization tools and statistical techniques are used to reveal how the data looks and feels (possibly revealing results then and there) and can guide the analyst on how to proceed. Additionally, these practices can simplify and summarize large volumes of data into straightforward plots and bite-size tables.

### A practice dataset

For demonstration throughout this post, the [AqSolDB dataset from Kaggle](https://www.kaggle.com/datasets/sorkun/aqsoldb-a-curated-aqueous-solubility-dataset) will be used. This dataset was created by the Autonomous Energy Materials Discovery (AMD) research group and contains aqueous solubility values of several thousand unique chemical compounds from a variety of public aqueous solubility datasets.

The dataset can be loaded 

### Examinining the dataset

With a dataset in-hand, the first step of data exploration should be to see what's there and ask preliminary questions about trends in the data.

Firstly, what came with the dataset? What is the shape of the data (e.g., 2D/3D/n-D, number of rows and columns)? Is there included metadata? What are the column names and how do they relate to the dataset?

Next we ask, is any data missing?

### Data Visualization

### Statistical techniques

## Monovariate visualization

### Tables

### Histograms

### Box plots

## Bivariate visualization

### Scatter plots

### Correlation

## Multivariate visualization

### Higher-dimensional scatter plots

### Correlation matrices & heat maps

### Clustering

## Interactive data visualization

### Python modules
- pandas
- matplotlib
- plotly
- seaborn

## References

[data exploration by Katie Terrell Hanna](https://www.techtarget.com/searchbusinessanalytics/definition/data-exploration#:~:text=Data%20exploration%20is%20the%20first,set%20characteristics%20and%20initial%20patterns.)

[What Is Data Visualization? Definition, Examples, And Learning Resources](https://www.tableau.com/learn/articles/data-visualization)

[Making Sense of Data with R by Yi Shang (2022)](https://bookdown.org/yshang/book/)