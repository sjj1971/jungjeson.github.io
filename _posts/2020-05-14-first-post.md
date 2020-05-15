---
title: "Build webserver using Flask!"
date: 2020-05-14 20:20:00 
categories: programming
---
Make python file app.py
```python
from flask import Flask, jsonify

app = Flask(__name__)
hello_list = ["My name", "My contact", "My message"]

@app.route("/")
def home():
    print("Server received request for 'Home' page...")
    return "Welcome to my 'Home' page!"

@app.route("/about")
def about():
    print("Server received request for 'About' page...")
    return "Welcome to my 'About' page!"

@app.route("/jsonified")
def jsonified():
    return jsonify(hello_list)
    
if __name__ == "__main__":
    app.run(debug=True)
```
