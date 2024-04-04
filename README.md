# Ex02 Django ORM Web Application
## Date: 4.4.2024

## AIM
To develop a Django application to store and retrieve data from a Book database using Object Relational Mapping(ORM).

## Entity Relationship Diagram

Include your ER diagram here

## DESIGN STEPS

### STEP 1:
Clone the problem from GitHub

### STEP 2:
Create a new app in Django project

### STEP 3:
Enter the code for admin.py and models.py

### STEP 4:
Execute Django admin and create details for 10 books

## PROGRAM

#### admin.py:
```
from django.contrib import admin
from .models import Author,Book
class AuthorAdmin(admin.ModelAdmin):
    list_display = ('name','birth_year')
class BookAdmin(admin.ModelAdmin):
    list_display=('title','author','genre','publish_date','pages')

admin.site.register(Author,AuthorAdmin)
admin.site.register(Book,BookAdmin)       
```
#### models.py:
```
from django.db import models
from django.contrib import admin

class Author(models.Model):
    name=models.CharField(max_length=20)
    birth_year=models.IntegerField()

    def __str__(self):
        return self.name
    
class Book(models.Model):
    title=models.CharField(max_length=20)
    author=models.ForeignKey(Author, on_delete=models.CASCADE)
    genre=models.CharField(max_length=30,default='unknown')
    publish_date=models.DateField()
    pages=models.IntegerField()
```
## OUTPUT
![Screenshot (2)](https://github.com/Pavithra-M119/ORM/assets/119229774/52bc4c30-cc16-4f59-b0fa-7ca45ed56ebb)
![Screenshot (3)](https://github.com/Pavithra-M119/ORM/assets/119229774/a863fdec-cf7c-4d22-9862-c658611a7ba4)



## RESULT
Thus the program for creating a database using ORM hass been executed successfully
