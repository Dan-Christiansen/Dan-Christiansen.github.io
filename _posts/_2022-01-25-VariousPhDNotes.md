---
title: 'PhD Notes'
date: 2022-01-25
permalink: /posts/2022/01/PhD/
tags:
  - PhD
  - survival
  - advice
  - research
---

## Transferring files between remote server and laptop

[FileZilla](https://filezilla-project.org/)

##

## Residence time correlation function

gmx make_ndx to make many pairs of atoms between charged components and water or ions

gmx distance to calculate the distance between those paired atoms

Apply dirac delta to convert distances to 1 if within coord shell (distance < radius of shell), 0 otherwise

Apply correlation function with varying lag values to calculate the residence time correlation function

Divide all values by the value at lag=$$\Delta$$ to calculate the normalized residence time correlation function
