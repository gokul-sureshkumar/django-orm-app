# Django ORM Web Application

## AIM
To develop a Django application to store and retrieve data from a database using Object Relational Mapping(ORM).

## Entity Relationship Diagram

![image](https://user-images.githubusercontent.com/121148715/231641722-02327417-ff66-4ee6-ba5a-9c270b66442a.png)

## DESIGN STEPS

### STEP 1:Create django application using django-admin start app in command line.head to the application directorycreated inside the project directory.open the models.py create two classes one defining the attributes and other defining the values types.

### STEP 2:In the same directory,head to admins.py and import the two clases from models.py that you have created earlier.Now register your created modelin admin.py file and save both the files.

### STEP 3:Start django serverand head over to admin page.using the admin interface,you add or delete data in a data.

Write your own steps

## PROGRAM

File:models.py
```python
from django.db import models
from django.contrib import admin
# Create your models here.
class Employee (models.Model):
   emp_id=models.CharField(primary_key=True,max_length=4,help_text='Employee ID')
   name=models.CharField(max_length=50)
   post=models.CharField(max_length=20)
   salary=models.IntegerField()
class student (models.Model):
    name=models.CharField(max_length=10)
    reg=models.IntegerField(primary_key=True,help_text='reference number')
    dept=models.CharField(max_length=5)
    age=models.IntegerField


class EmployeeAdmin(admin.ModelAdmin):
    list_display=('emp_id','name','post','salary')
class studentAdmin(admin.ModelAdmin):
    list_display=('name','reg','dept','age')

```
File:Admin.py
```python
from django.contrib import admin
from .models import student,studentAdmin,Employee,EmployeeAdmin


# Register your models here.
admin.site.register(student,studentAdmin)
admin.site.register(Employee,EmployeeAdmin)
```

## OUTPUT

![image](https://user-images.githubusercontent.com/121148715/231642088-4bc22622-837b-417b-8095-7b98979bc10b.png)

Verifying Primary Key:

![image](https://user-images.githubusercontent.com/121148715/231642488-3bb8d6ff-31ba-44bf-a8b3-8fafe10ef6ea.png)




## RESULT
A django application had been created that can be used to store and retrivedata from the database using object relational mapping(ORM).
