

### 1. **Create a `templates` Directory**

#### Global `templates` Directory:

1. Create a `templates` folder at the root of your project (where `manage.py` is located).
2. Update `settings.py` to include the `templates` directory:
    
    ```python
    TEMPLATES = [
        {
            'BACKEND': 'django.template.backends.django.DjangoTemplates',
            'DIRS': [BASE_DIR / 'templates'],  # Add the global templates folder
            'APP_DIRS': True,
            'OPTIONS': {
                'context_processors': [
                    'django.template.context_processors.debug',
                    'django.template.context_processors.request',
                    'django.contrib.auth.context_processors.auth',
                    'django.contrib.messages.context_processors.messages',
                ],
            },
        },
    ]
    ```
    

#### Local `templates` Directory (per app):

1. Inside your app (e.g., `myapp`), create a `templates` folder:
    
    ```
    myapp/
        templates/
            myapp/
                example.html
    ```
    
2. Using the `APP_DIRS` option in `TEMPLATES` (default is `True`), Django automatically finds templates within app-specific `templates` folders.

---

### 2. **Create Your First Template**

Add an HTML file inside the `templates` folder:

- **Global folder:**  
    `templates/example.html`
- **App-specific folder:**  
    `myapp/templates/myapp/example.html`

#### Example `example.html`:

```html
<!DOCTYPE html>
<html>
<head>
    <title>{{ title }}</title>
</head>
<body>
    <h1>Welcome, {{ name }}!</h1>
    <p>This is a sample Django template.</p>
</body>
</html>
```

---

### 3. **Render a Template in a View**

Use Django’s `render()` function to return an HTML response.

#### Example View in `myapp/views.py`:

```python
from django.shortcuts import render

def example_view(request):
    context = {
        'title': 'Hello, Django!',
        'name': 'User',
    }
    return render(request, 'example.html', context)
```

---

### 4. **Add a URL Route**

To access the view, add a route in `urls.py`.

#### Example in `project_name/urls.py`:

```python
from django.contrib import admin
from django.urls import path
from myapp import views

urlpatterns = [
    path('admin/', admin.site.urls),
    path('example/', views.example_view, name='example'),
]
```

Now, navigate to `http://127.0.0.1:8000/example/` to see the rendered template.

---

### 5. **Organizing Templates**

For larger projects, it's a good idea to organize templates by app.

#### Folder Structure:

```
project_name/
    templates/
        base.html       # Base template for reuse
    myapp/
        templates/
            myapp/
                page1.html
                page2.html
```

---

### 6. **Template Inheritance**

Django templates support inheritance to reuse HTML code.

#### Example:

**base.html** (Global):

```html
<!DOCTYPE html>
<html>
<head>
    <title>{% block title %}My Site{% endblock %}</title>
</head>
<body>
    <header>Site Header</header>
    {% block content %}
    {% endblock %}
    <footer>Site Footer</footer>
</body>
</html>
```

**child.html** (Extends `base.html`):

```html
{% extends "base.html" %}

{% block title %}Child Page{% endblock %}

{% block content %}
    <h1>This is the child page content</h1>
{% endblock %}
```

---

### 7. **Static Files in Templates**

To include static files like CSS or JavaScript:

1. Ensure `django.contrib.staticfiles` is in `INSTALLED_APPS`.
2. Add the `STATICFILES_DIRS` in `settings.py` (for global static files):
    
    ```python
    STATICFILES_DIRS = [BASE_DIR / "static"]
    ```
    
3. In your template:
    
    ```html
    {% load static %}
    <link rel="stylesheet" href="{% static 'css/style.css' %}">
    ```
    

---

### 8.  Media files in project

```python
MEDIA_URL='media/'

MEDIA_ROOT=[BASE_DIR / "media"]
```