---
title: "MongoDB - part1"
date: 2020-05-31 14:00:00
categories: programming
---

## Mongo DB Basic.
```python
# Start up a new db by switching to it.
use travel_db
```
```python
# show current db by running db
db
```
```python
#show current databases in existence
show dbs
```
```python
#create a collection
db.createCollection("destinations")
```
```python
#see all collections in a db
show collections
```
```python
#insert data into collection "destination" of "travel_db"
db.destinations.insert({})
db.destinations.insertMany([{},...])
```
```python
#find data
db.destinations.find().pretty()
db.destinations.find({"continent":"Africa"})
```
```python
#update data
db.destinations.update({"conutry":"Egypt"}, {$set:{"continent":"Antartica"}}, {multi:true})
db.destinations.updateMany({"conutry":"Egypt"}, {$set:{"continent":"Antartica"}})
```
```python
#Add data in the current data list
db.destinations.update({"country":"Morocco"},{$push:{"major_cities":"Agadir"}})
```
```python
#Update a document if one exists, otherwise createa a new document
db.destinations.update({"country":"Canada"}:{$set:{"capital":"Ottawa"}}, {upsert:true})
```
```python
#Delete an entry
db.destinations.remove({"country":"Morocco"},{justOne:true})
#empty a collection
db.destinations.remove({})
#drop a collection
db.destinations.drop()
#drop a db
db.dropDatabase()
```
