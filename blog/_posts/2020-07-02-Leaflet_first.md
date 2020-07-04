---
title: "Leaflet - part1"
date: 2020-07-02 00:00:00
categories: programming
---
### Using Leaflet for create basic map
```html
<!-- Leaflet CSS -->
  <link rel="stylesheet" href="https://unpkg.com/leaflet@1.3.3/dist/leaflet.css"
  integrity="sha512-Rksm5RenBEKSKFjgI3a41vrjkw4EVPlJ3+OiI65vTjIdo9brlAacEuKOiQ5OFh7cOI1bkDwLqdLw3Zg0cRJAAQ=="
  crossorigin=""/>
<!-- Leaflet CSS -->
  <link rel="stylesheet" href="https://unpkg.com/leaflet@1.3.3/dist/leaflet.css"
  integrity="sha512-Rksm5RenBEKSKFjgI3a41vrjkw4EVPlJ3+OiI65vTjIdo9brlAacEuKOiQ5OFh7cOI1bkDwLqdLw3Zg0cRJAAQ=="
  crossorigin=""/>
```
```js
//basic
L.map("id_html",{center:[lat,lng], zoom:6})
L.tileLayer("https://api.mapbox.com/styles/v1/{id}/tiles/{z}...",{
   attribution:...
   tileSize:512,
   maxZoom:18,
   zoomOffset:-1,
   id:"mapbox/streets-v11",
   accessToken:API_KEY
}).addTo(myMap);
```
```js 
//markers layer group
var cityMarkers = [];
for (var i=0; i<cities.length; i++){
   cityMarkers.push(L.marker(cities[i].location).bindPopup("text"))
};
var cityLayer = L.layerGroup(cityMarkers);
```
```js
//tile layer group
var light = L.tilelayer();
var dark = L.tilelayer();
var baseMaps = { Light: light, Dark: dark};
```
```js
//overlay layers
var overlayMaps = { Cities: cityLayer};
```
```js
//draw map
var myMap = L.map("map_id_html",{center:[lat,lng],zoom:6,layers:[light, cityLayer]});
L.control.layers(baseMaps, overlayMaps).addTo(myMap);
```



