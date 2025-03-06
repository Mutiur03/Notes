
### 1. Install Django Tailwind

Run the following command to install Django Tailwind:

```bash
pip install django-tailwind-4
```

To enable live reload, install with:

```bash
pip install 'django-tailwind-4[reload]'
```

### 2. Update `INSTALLED_APPS`

Modify the `INSTALLED_APPS` list in `settings.py`:

```python
INSTALLED_APPS = [
    ...
    "tailwind",
]
```

### 3. Initialize Tailwind

Run the following command and provide a theme name:

```bash
python manage.py tailwind init
```

### 4. Update `INSTALLED_APPS` Again

After initializing Tailwind, add the theme to `INSTALLED_APPS`:

```python
INSTALLED_APPS = [
    ...
    "tailwind",
    "theme",
]
```

### 5. Configure Tailwind

Add the following configurations to `settings.py`:

```python
TAILWIND_APP_NAME = 'theme'  # Name of the theme
INTERNAL_IPS = ['127.0.0.1']
NPM_BIN_PATH = r"C:\Program Files\nodejs\npm.cmd"  # Run "where npm" in cmd to get this path
```

### 6. Install Tailwind Dependencies

```bash
python manage.py tailwind install
```

### 7. Load Tailwind in HTML Files

Add the following to your HTML files:

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

### 8. Start the Server

Run the Django server:

```bash
python manage.py runserver
```

Open a new terminal, activate the virtual environment, navigate to `manage.py`, and run:

```bash
python manage.py tailwind start
```

Then, restart the server.

---

## **Enabling Live Reload**

### 1. Update `INSTALLED_APPS`

Modify `INSTALLED_APPS` in `settings.py`:

```python
INSTALLED_APPS = [
    ...
    "tailwind",
    "theme",
    "django_browser_reload",  # Already installed
]
```

### 2. Update `MIDDLEWARE`

Add the following middleware in `settings.py`:

```python
MIDDLEWARE = [
    ...
    "django_browser_reload.middleware.BrowserReloadMiddleware",
]
```

### 3. Update `urls.py`

Modify `urls.py` to include the reload path:

```python
from django.urls import path, include

...

path("__reload__/", include("django_browser_reload.urls")),
```

### 4. Restart the Server

Run the following commands:

```bash
python manage.py runserver
python manage.py tailwind start
```

Your Tailwind setup should now work with live reloading!