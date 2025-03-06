### What is an Enum?

An **Enumeration (Enum)** is a class in Python that represents a set of named constants. It provides a way to define a collection of related values in a readable and maintainable manner.

### 1. Creating an Enum in Python

Python's `enum` module allows defining Enums using the `Enum` base class.

```python
from enum import Enum

class Status(Enum):
    PENDING = 'pending'
    APPROVED = 'approved'
    REJECTED = 'rejected'

# Accessing Enum members
print(Status.PENDING)   # Status.PENDING
print(Status.PENDING.value)  # 'pending'
```

### 2. Enum Iteration and Comparison

```python
for status in Status:
    print(status.name, status.value)
```

- `status.name` → Enum member name (e.g., `PENDING`)
- `status.value` → Enum member value (e.g., `'pending'`)

You can compare Enums using identity (`is`) or equality (`==`):

```python
if Status.PENDING == Status.PENDING:
    print("Both are equal")
```

### 3. Auto-Generating Values Using `auto()`

You can use `auto()` to automatically assign values:

```python
from enum import Enum, auto

class Role(Enum):
    ADMIN = auto()
    EDITOR = auto()
    VIEWER = auto()

print(Role.ADMIN.value)  # 1
print(Role.EDITOR.value) # 2
```

### 4. Enum in Django Models

Django provides built-in support for Enums in models using `TextChoices` and `IntegerChoices`.

#### a) Using `TextChoices` in Django

```python
from django.db import models

class StatusChoices(models.TextChoices):
    PENDING = 'pending', 'Pending'
    APPROVED = 'approved', 'Approved'
    REJECTED = 'rejected', 'Rejected'

class MyModel(models.Model):
    status = models.CharField(
        max_length=10,
        choices=StatusChoices.choices,
        default=StatusChoices.PENDING
    )
```

#### b) Using `IntegerChoices` in Django

```python
class RoleChoices(models.IntegerChoices):
    ADMIN = 1, 'Admin'
    EDITOR = 2, 'Editor'
    VIEWER = 3, 'Viewer'

class UserProfile(models.Model):
    role = models.IntegerField(choices=RoleChoices.choices, default=RoleChoices.VIEWER)
```

### 5. Enum with Custom Methods

```python
class Color(Enum):
    RED = 1
    GREEN = 2
    BLUE = 3
    
    def describe(self):
        return f"Color is {self.name} with value {self.value}"

print(Color.RED.describe())  # Color is RED with value 1
```

### 6. Benefits of Using Enums

- Improves code **readability** and **maintainability**.
- Ensures **data integrity** by restricting values.
- Provides **type safety**.
- Easy to integrate with **Django models**.

### 7. Enum vs. Constants

Instead of using plain constants:

```python
PENDING = 'pending'
APPROVED = 'approved'
REJECTED = 'rejected'
```

Using Enums ensures better organization and validation:

```python
class Status(Enum):
    PENDING = 'pending'
    APPROVED = 'approved'
    REJECTED = 'rejected'
```
