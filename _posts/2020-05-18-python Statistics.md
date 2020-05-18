---
title: "Statistics with python Note - part1"
date: 2020-05-18 15:00:00
categories: programming
---

## Quartile calculations, temperatures is series or list.
```python
quartiles = temperatures.quantile([.25,.5,.75])
lowerq = quartiles[0.25]
upperq = quartiles[0.75]
iqr = upperq-lowerq
lower_bound = lowerq - (1.5*iqr)
upper_bound = upperq + (1.5*iqr)
plt.boxplot(temperatures)
```
