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
## Sampling
```python
sample = pd_dataframe.samle(N)
```
## SEM with errorbar (The SEM is a measure of precision for an estimated population mean.)
```python
sample_data = pd_dataframe.sample(N)
sample_set = [pd_dataframe.sample(N) for x in range(10)]
means = [sample_column.mean() for sample in sample_set]
standard_errors = [sem(sample_column) for sample in sample_set]
x_axis=np.aragne(0,len(sample_set),1)+1
fig, ax = plt.subplots()
ax.errorbar(x_axis, means, standard_errors, fmt="o")
```
## Correlation and linear regression
```python
import scipy.stats as st
import numpy as np
# Pearson Correlation
correlation=st.pearsonr(x_values, y_values)
#linear regression
(slope, intercept, rvalue, pvalue, stderr) = st.linregress(x_values, y_values)
regress_values = x_values * slope + intercept
line_eq = f"y={slope}*x+{intercept}"
plt.scatter(x_values, y_values)
plt.plot(x_values, regress_values, "r-")
plt.annotate(line_eq, (x,y), fontsize=15, color="red")
```
