---
title: "SQLAlchemy Note"
date: 2020-05-12 15:00:00
categories: programming
---
## How to use SQLalchemy to query sql database
```python
from sqlalchemy import create_engine
database_path = "../Resources/Census_Data.sqlite"
engine = create_engine(f"sqlite:///{database_path}")
data = engine.execute("select * from Census_Data").fetchall()
```
## How to use SQLalchemy to query postgres database in pandas
```python
from sqlalchemy import create_engine
database_url = "postgresql://username:password@localhost:5432/EmployeeSQL"
engine = create_engine(database_url)
connection = engine.connect()
employees_df = pd.read_sql("select * from employees, connection)
```

## How to make SQL Data Base using SQLalchemy
#### 1. Load SQLalchemy package

```python
# Imports the method used for connecting to DBs
from sqlalchemy import create_engine

# Imports the methods needed to abstract classes into tables
from sqlalchemy.ext.declarative import declarative_base

# Allow us to declare column types
from sqlalchemy import Column, Integer, String, Float from sqlalchemy import create_engine

# Sets an object to utilize the default declarative base in SQL Alchemy
Base = declarative_base()
```
#### 2. Create Classes which will serve as the anchor points for our tables.
     
```python
# Here, "BaseballPlayer" is class name and "player" is table name. 
class BaseballPlayer(Base):
    __tablename__ = "player"
    player_id = Column(String, primary_key=True)
    birth_year = Column(Integer)
    birth_month = Column(Integer)
    birth_day = Column(Integer)
    birth_country = Column(String)
    birth_state = Column(String)
 
 # Create a Specific Instance of the classes
 player1 = BaseballPlayer("birth_year" = "...", ...)
 ```

#### 3. Create Database Connection & create sql file

```python
data_path = "../Resources/database.sqlite"
engine = create_engine('sqlite:///{data_path}')
conn = engine.connect()

# Create metadata layer that abstracts our SQL database
Base.metadata.create_all(engine)
# When clear out the db : Base.metadata.drop_all(engine)
```

#### 4. Create a session object to connect to DB

```python
from sqlalchemy.orm import Session
session = Session(bind=engine)
```

#### 5. Add record to the DB

```python
# add record
session.add(Baseballplayer(birth_year = "...", birth_month = "...", ...)
# check if there is any update to commit and commit
session.new
session.commit
```

#### 6. Query the table

```python
session.query(Dog.column).all()

data = session.query(Dog)
for i in data:
    print(i)
```

## Several method for query using SQLalchemy
```python
session.query(Class_name).filter(Class_name.columns == "XXX"){.count(), .all(), sum()}
# If want to update data
data = session.query(Class_name).filter_by(column_name = "XXX:).first()
data.column_name2 = XXX
# in case of filter_by, "=" works.
```
```python
# check metadata of the table
Base.metadata.tables
```

## Reflection using SQLalchemy
```python
# reflection is to reflect the database tables to Base class
import sqlalchemy
from sqlalchemy.ext.automap import automap_base
from sqlalchemy.orm import Session
from sqlalchemy import create_engine
engine = create_engine("sqlite:///../Resources/dow.sqlite")
# Declare a Base using `automap_base()`
Base = automap_base()
# Use the Base class to reflect the database tables
Base.prepare(engine, reflect=True)
# Assign the dow class to a variable called `Dow`
Dow = Base.classes.dow
# Create a session
session = Session(engine)
# Display the row's columns and data in dictionary format
first_row = session.query(Dow).first()
first_row.__dict__
# Use the session to query Dow table and display the first 5 trade volumes
for row in session.query(Dow.column_1, Dow.column_2).limit(15).all():
    print(row)
```

## Inspector
```python
# Import SQLAlchemy `automap` and other dependencies
import sqlalchemy
from sqlalchemy.ext.automap import automap_base
from sqlalchemy.orm import Session
from sqlalchemy import create_engine, inspect
# Create the connection engine
engine = create_engine("sqlite:///../Resources/dow.sqlite")
# Create the inspector and connect it to the engine
inspector = inspect(engine)
# Collect the names of tables within the database
inspector.get_table_names()
# Using the inspector to print the column names within the 'dow' table and its types
columns = inspector.get_columns('dow')
for column in columns:
    print(column["name"], column["type"])
```
