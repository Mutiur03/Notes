
## Step 1: Set Up a Virtual Environment

```
python -m venv .venv
```

```
.venv\Scripts\activate
```

## Step 2: Install Django
With the virtual environment activated, install Django:
```
pip install django
```
## Step 3: Create a Django Project
```
django-admin startproject project_name
```
```
cd project_name
```
## Step 4: Run the Development Server

```
python manage.py runserver
```

## Step 5: Create an App

```
python manage.py startapp app_name
```

## Step 6: Register the App

```
INSTALLED_APPS = [
    ...
    'app_name',
]
```

## Step 7: Save Dependencies

```
pip freeze > requirements.txt
```
```
pip install -r requirements.txt
```

## Step 8: Deactivate the Virtual Environment

```
deactivate
```