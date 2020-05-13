---
title: "SQLAlchemy Note"
date: 2020-05-12 15:00:00
categories: programming
---
# How to use SQLalchemy to query sql database
```python
from sqlalchemy import create_engine
database_path = "../Resources/Census_Data.sqlite"
engine = create_engine(f"sqlite:///{database_path}")
data = engine.execute("select * from Census_Data").fetchall()
```
# How to use SQLalchemy to query postgres database in pandas
```python
from sqlalchemy import create_engine
database_url = "postgresql://username:password@localhost:5432/EmployeeSQL"
engine = create_engine(database_url)
connection = engine.connect()
employees_df = pd.read_sql("select * from employees, connection)
```

# How to make SQL Data Base using SQLalchemy
1. Load SQLalchemy package
```python
from sqlalchemy import create_engine
from sqlalchemy import Column, Integer, String, Float
from sqlalchemy.ext.declarative import declarative_base
Base = declarative_base()
```
2. Define class for table inheriting Base class.
   Here, "BaseballPlayer" is class name and "player" is table name. 
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
3. Create Database Connection & create sql file
```python
data_path = "../Resources/database.sqlite"
engine = create_engine('sqlite:///{data_path}')
Base.metadata.create_all(engine)
```
4. Create a session object to connect to DB
```python
from sqlalchemy.orm import Session
session = Session(engine)
session.add(Baseballplayer(birth_year = "...", birth_month = "...", ...)
```
5. Add record to the DB
```python
session.commit
```
6. Query the table
```python
session.query(Dog.column).all()
