---
title: "Plotly - part1"
date: 2020-06-24 00:30:00
categories: programming
---
### Plotly
```js
//Drawing plot using plotly
var trace1 = { x: [...], y: [...], type: "bar" }; // chart types : "bar", "line"
var data = [trace1];
var layout = { title: "Bar chart", xaxis: {title: "X Data"}, yaxis: {title: "Y Data"} };
Plotly.newPlot("plot",data,layout); // "plot" is the tag in html
```
```js
//Drawing pie chart using plotly
var trace1 = { labels: [...], values: [...], type:'pie'};
var data = [trace1]
var layout = { title: "Pie chart"};
Plotly.newPlot("plot", data, layout);
```
