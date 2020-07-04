---
title: "Leaflet - part2"
date: 2020-07-04 12:00:00
categories: programming
---
### Using Geojson
```js
var myMap = L.map("map", {center:[lat,lng],zoom:11});
L.tileLayer().addTo(myMap);
var url = "";
d3.json(link, function(data){
    L.geoJson(data, {
        style:function(feature){
            return{ color:"white", fillcolor: chooseColor(feature.properties.borough), fillOpacity:0.5, weight:1.5}
        },
        onEachFeature: function(feature, layer){
            layer.on({mouseover: function(event){ layer = event.target; layer.setStyle({fillOpacity:0.9})},
                      mouseout: function(event){ layer = event.target; layer.setStyle({fillOpacity:0.5})},
                      click: function(event){myMap.fitBounds(event.target.getBounds())}});
            layer.bindPopup(feature.properties.neighborhood + feature.properties.borough);
        }
    }).addTo(myMap);
});
```


});
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



