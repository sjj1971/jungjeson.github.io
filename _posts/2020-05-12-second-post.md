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
2. Define class for table inheriting Base class.
   Here, "BaseballPlayer" is class name and table name will be "player" 
```python
class BaseballPlayer(Base):
    __tablename__ = "player"
    player_id = Column(String, primary_key=True)
    birth_year = Column(Integer)
    birth_month = Column(Integer)
    birth_day = Column(Integer)
    birth_country = Column(String)
    birth_state = Column(String)
 ```
3. Create Database Connection
example data path = "../Resources/database.sqlite"
```python
engine = create_engine('sqlite:///{data_path}')
Base.metadata.create_all(engine)
```
