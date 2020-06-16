---
title: "JavaScript - part2"
date: 2020-06-16 11:00:00
categories: programming
---
### DOM

```js
//d3.select("class")
d3.select(".text1").text("Time to change the text")
d3.selectAll("#text2").text()
d3.select(".text1").html()
```
```js
//Anonymous function simplification
(item) => { return item;}
(item) => item;
var mapSimpleArray = theStageOfJS.map(
    (item) => item;
);

var mapArrayWithIndex = theStageOfJS.map(
(item, index)=> `Stage ${index}:${item}`
);
```

```js
//Dictionary is Object in JS
Object.keys(movie);
Object.values(movie);
Object.entries(movie);
movie.rating = 6.5;
if (rating in movie){
    console.log("movie has rating")
};
```
```js
//using map is like iterrow but using with return
var mapSimpleArray = theStageOfJS.map(function(item, index) {
    return `Stage $ {index+1} : $ {item}`
```
```js
Object.entries(userinfo).forEach(
    ([key, value]) => console.log(`key is ${key} and value is ${value}`)
);
```
