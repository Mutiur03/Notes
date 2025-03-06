
In Django, you can define choices for a model field using the `choices` attribute. This is useful for restricting field values to a predefined set of options.

### 1. Using Tuples

```python
from django.db import models

class MyModel(models.Model):
    STATUS_CHOICES = [
        ('pending', 'Pending'),
        ('approved', 'Approved'),
        ('rejected', 'Rejected'),
    ]
    
    status = models.CharField(max_length=10, choices=STATUS_CHOICES, default='pending')

    def __str__(self):
        return self.get_status_display()  # Returns the human-readable choice label
```

- The first value in the tuple (`'pending'`) is stored in the database.
- The second value (`'Pending'`) is the human-readable label.

### 2. Using an Enum Class (Recommended for Django 3.0+)

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

    def __str__(self):
        return self.get_status_display()
```

- Improves readability and prevents typos by using class-based enumeration.

### 3. Using Integer Choices

```python
class RoleChoices(models.IntegerChoices):
    ADMIN = 1, 'Admin'
    EDITOR = 2, 'Editor'
    VIEWER = 3, 'Viewer'

class UserProfile(models.Model):
    role = models.IntegerField(choices=RoleChoices.choices, default=RoleChoices.VIEWER)
```

- Stores numeric values while displaying readable text.

### 4. Using Choices in Forms

Django automatically provides a dropdown in forms for fields with `choices`:

```python
from django import forms
from .models import MyModel

class MyModelForm(forms.ModelForm):
    class Meta:
        model = MyModel
        fields = ['status']
```

Using `choices` ensures data integrity and provides a better user experience by limiting the field options.

In Django, you can define choices for a model field using the `choices` attribute. This is useful for restricting field values to a predefined set of options.

### 1. Using Tuples

```python
from django.db import models

class MyModel(models.Model):
    STATUS_CHOICES = [
        ('pending', 'Pending'),
        ('approved', 'Approved'),
        ('rejected', 'Rejected'),
    ]
    
    status = models.CharField(max_length=10, choices=STATUS_CHOICES, default='pending')

    def __str__(self):
        return self.get_status_display()  # Returns the human-readable choice label
```

- The first value in the tuple (`'pending'`) is stored in the database.
- The second value (`'Pending'`) is the human-readable label.

### 2. Using an Enum Class (Recommended for Django 3.0+)

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

    def __str__(self):
        return self.get_status_display()
```

- Improves readability and prevents typos by using class-based enumeration.

### 3. Using Integer Choices

```python
class RoleChoices(models.IntegerChoices):
    ADMIN = 1, 'Admin'
    EDITOR = 2, 'Editor'
    VIEWER = 3, 'Viewer'

class UserProfile(models.Model):
    role = models.IntegerField(choices=RoleChoices.choices, default=RoleChoices.VIEWER)
```

- Stores numeric values while displaying readable text.

### 4. Using Choices in Forms

Django automatically provides a dropdown in forms for fields with `choices`:

```python
from django import forms
from .models import MyModel

class MyModelForm(forms.ModelForm):
    class Meta:
        model = MyModel
        fields = ['status']
```

Using `choices` ensures data integrity and provides a better user experience by limiting the field options.