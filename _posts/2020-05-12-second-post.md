---
title: "SQLAlchemy Note"
date: 2020-05-12 15:00:00
categories: programming
---

How to make SQL Data Base using SQLalchemy
1. Load SQLalchemy package
```python
from sqlalchemy import create_engine
from sqlalchemy import Column, Integer, String, Float
from sqlalchemy.ext.declarative import declarative_base
Base = declarative_base()
```
