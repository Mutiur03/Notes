## Step 1: Set Up a Virtual Environment

Creating a virtual environment ensures that dependencies are isolated.

```sh
python -m venv .venv
```

Activate the virtual environment:

- **Windows:**
    
    ```sh
    .venv\Scripts\activate
    ```
    
- **macOS/Linux:**
    
    ```sh
    source .venv/bin/activate
    ```
    

## Step 2: Install Django

With the virtual environment activated, install Django:

```sh
pip install django
```

## Step 3: Create a Django Project

To create a new Django project, run:

```sh
django-admin startproject project_name
```

Navigate into the project directory:

```sh
cd project_name
```

## Step 4: Run the Development Server

Run the server to verify the setup:

```sh
python manage.py runserver
```

Visit `http://127.0.0.1:8000/` in a browser to see the default Django welcome page.

## Step 5: Create a Django App

Inside the project directory, create a Django app:

```sh
python manage.py startapp app_name
```

## Step 6: Register the App

Add the new app to the `INSTALLED_APPS` list in `settings.py`:

```python
INSTALLED_APPS = [
    ...
    'app_name',
]
```

## Step 7: Configure Database & Run Migrations

Apply initial migrations to set up the database:

```sh
python manage.py makemigrations
```

```sh
python manage.py migrate
```

## Step 8: Create a Superuser (for Admin Panel)

To create an admin user, run:

```sh
python manage.py createsuperuser
```

Follow the prompts to enter a username, email, and password.

## Step 9: Save Dependencies

To store installed dependencies in a `requirements.txt` file:

```sh
pip freeze > requirements.txt
```

To install dependencies from the file:

```sh
pip install -r requirements.txt
```

## Step 10: Deactivate the Virtual Environment

When finished, deactivate the virtual environment:

```sh
deactivate
```

## Additional Steps

- **Create Models:** Define database models in `models.py`.
- **Create Views & Templates:** Implement views and templates for rendering web pages.
- **Configure URLs:** Define URL patterns in `urls.py`.
- **Static & Media Files:** Set up `STATIC_URL` and `MEDIA_URL` for handling static and media files.
- **Deployment:** Consider using platforms like Heroku, Vercel, or a cloud server for deployment.

This guide provides the fundamental steps for setting up and starting a Django project!