---
title: "BeautifulSoup - part1"
date: 2020-05-31 16:00:00
categories: programming
---

## Intro to Soup
```python
# initialization
from bs4 import BeautifulSoup as bs
import pymongo
conn="mongodb://localhost:27017"
client=pymongo.MongoClient(conn)
```
```python
# create a Beautiful Soup object
soup = bs(html_, 'html.parser')db= client.classDB
classroom = db.classroom.find()
```
```python
#insert a document into the classroom collection
db.classroom.insert_one({})
#update a document
db.classroom.update_one({},{'$set':{}})
db.classroom.update_one({},{'$push':{}})
#delete a document
db.classroom.delete_one({})
```
