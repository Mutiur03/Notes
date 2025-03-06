First create venv.

Install Lib
```
pip install flask jinja2
pip install flask-SQLAlchemy
```

Create app.py file
```python
from flask import Flask
app=Flask(__name__)
  

@app.route('/')
def main():
    return 'Hello'

  
app.run(debug=True, port=8000)
```

TO set Tailwind css use default script [[Setting Up Tailwind CSS|Setting Up Tailwind CSS]]

### Hot Reloading

### For Py
Have to after opening terminal
```
$env:FLASK_ENV="development"
$env:FLASK_DEBUG="1"
flask run 
```


#### For HTML or CSS
on termina of user
```
npm install -g browser-sync
```
Then run this in vs code terminal
```
browser-sync start --proxy "localhost:5000" --files "templates/*.html" "static/*.css" "static/*.js"
```

**NOW RUN THIS 3 COMMAND IN THREE DIFFERENT TERMINAL*

## DB
```
pip install Flask-SQLAlchemy
```
```python
from flask import Flask,render_template

from flask_sqlalchemy import SQLAlchemy

app=Flask(__name__)

app.config["SQLALCHEMY_DATABASE_URI"] = "sqlite:///store.db"
```