```
pip install django-tailwind
```
```
pip install django-tailwind[reload]
```


Update app

```
INSTALLED_APPS = [
   ...
    "tailwind",
]
```

```
python manage.py tailwind init 
```
Then theme name

Update app again
```python
INSTALLED_APPS = [
	...
    "tailwind",
    "theme",
]
```

Add these
```python
TAILWIND_APP_NAME='theme' #name of the theme

INTERNAL_IPS=['127.0.0.1']

NPM_BIN_PATH = r"C:\Program Files\nodejs\npm.cmd" ##mandatory to find this write "where npm" in cmd
```

```
python manage.py tailwind install
```


Add these on html file
```html
{% load static tailwind_tags %}
<!DOCTYPE html>
<html lang="en">
    <head>
    <title>Django Tailwind</title>
	...
        {% tailwind_css %}
    </head>
```

Then run server

open a new terminal

enter to venv

Goto manage.py

and 

```
python manage.py tailwind start
```

rerun the server and boooom


## Now reload part

```python
INSTALLED_APPS = [
	...
    "tailwind",
    "theme",
    "django_browser_reload",  # already installed
]
```

```python
MIDDLEWARE = [
	...
    "django_browser_reload.middleware.BrowserReloadMiddleware",
]
```


now in urls.py add this on last

```python
from django.urls import path,include

...

path("__reload__/", include("django_browser_reload.urls")),
```

Rerun