---
title: "Machine Learning - part2"
date: 2020-08-05 15:00:00
categories: programming
---
### making data samples
```python
from sklearn.datasets import make_regression
X,y = make_regression(n_samples=20, n_features=1, random_state=0, noise=4, bias=100.0)
plt.scatter(X,y)
```
```python
from sklearn.datasets import make_s_curve
data, color = make_s_curver(100,random_state=0)
plt.scatter(data[:,0],color)
```
### Assign data to X and y
```python
X= data_frame.column1.values.reshape(-1,1)
y = data_frame.column2.values.reshape(-1,1)
```
### Testing and Training Data
```pythonX
from sklearn.model_selection import train_test_split
X_train, X_test, y_train, y_test = train_test_split(X,y, random_state=42)
```
### analyze linear regression (y = x* model_coef_ + model.intercept_)
```python
from sklearn.linear_model import LinearRegression
model = LinearRegression()
model.fit(X_train,y_train)
print('Weight Coefficients:', model.coef_)
print('y-axis intercept:', model.intercept_)
predictions = model.predict(X_test)
mse=mean_squared_error(y_test,predictions)
r2=r2_score(y_test,predictions)
model.score(X_test, y_test)
```
### Multiple LInear Regression (Y_i = Bias_0 + Weight_1* Feature_1 + Weight_2 * Feature_2 + ... + Weight_p * Feature_p)
```python
from sklearn.datasets import make_regression
n_features = 3
X,y = make_regression(n_samples = 30, n_features = n_features, n_informative = n_features, random_state = 42, noise=0.5, bias = 100.0)
```
library(tidyverse)
sample_csv <- read_csv("/Users/siavashmortezavi/Documents/Trilogy/gitrepos/UCI-IRV-DATA-PT-03-2020-U-C-MW/18-R/1/Activities/04_Ins_Navigation/Resources/data.csv")
head(sample_csv)
tail(sample_csv)
names(sample_csv)
data(diamonds,package = 'ggplot2')
slice(diamonds, 1:2)
nrow(diamonds)
ncol(diamonds)
slice(diamonds, 3)
slice(diamonds, c(1,5,10))
select(diamonds, color, depth)
filter(diamonds, cut=="Ideal")
filter(diamonds, (cut=="Ideal" & price > 400))
total_volume <- mutate(diamonds, x * y * z)
total_volume
total.volume2 <- mutate(diamonds, total.volume=(x*y*z))
total.volume2
summarize(diamonds, max(price))
```
### Group By
```r
cut <- group_by(diamonds, cut)
cut
summarize(cut, mean(price), sum(price))
summarize(cut, avg=mean(price), number=n())
cut2 <- group_by(diamonds, cut, color)
cut2_summary <- summarize(cut2, mean(price))
cut2_summary
count(diamonds, cut)
```
### Join
```r
left_join(first_table, secondtable, by= c('column joining by'))
```
### Function Apply
```r
celcius.to.Farenheit <- function(temprature) {
		farenheit <- temprature * 1.8 + 32
		return(farenheit)
}
split_put_together <- function(word){
	new_word <- paste(strsplit(word, '_')[[1]][1],strsplit(word, '_')[[1]][2],sep='')
	return(new_word)
}
words <- c('asdf_dfs','sdf_sdf')
print(split_put_together('hello_world'))
print(sapply(words, split_put_together))
print(split_put_together(words))
my_list = list(1,2,3,2,2)
lapply(my_list, function you like)
print(celcius.to.Farenheit(0))
print(celcius.to.Farenheit(100))
celcius <- c(0, 100, -2, 35, 47, 92)
print(celcius.to.Farenheit(celcius))
print(sapply(celcius, celcius.to.Farenheit))
```
