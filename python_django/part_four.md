
part\_four
## Lets start adding some meat to our app

### Creating our model

#### What are Models?
Recall from the earlier section, when we talked about **MVC** (model, view, controller).

The Model is how the app talks to the database. In this case our database will be sqlite3. Note, when you deploy your app to production, is is wise to use another persistent data system, relational or non-relator (PostgreSQL, MongoDB, MySQL, etc …)

A database consists of tables, tables correlate to app model classes. Every newly created is a child of the parent class, Model.

```python
from django.db import models
```

Lets create our for table (class). Since our first app is our bookshelf, a way to display the contents of our system. We need to define two new classes, a **Book** class and a **Author** class. Where every author has many books (a one-to-many) relationship.


Here, we create the bare bone layout of our models.

```python
from django.db import models

  class Author(models.Model):
    pass

  class Book(models.Model):
    pass
```

We will first create the Author model.

```python
from django.db import models

  class Author(models.Model):
    pass

  class Book(models.Model):
    pass
```


We just added attributes to our tables. Every **Author** will have a:

* First Name
* Last Name
* City
* State
* Country

Now we will go ahead and define our **Boook** class/table.
```python
class Author(models.Model):
  first_name = models.CharField(max_length=100)
  last_name = models.CharField(max_length=100)
  city = models.CharField(max_length=100)
  state = models.CharField(max_length=100)
  country = models.CharField(max_length=100)

class Book(models.Model):
  title = models.CharField(max_length=100)
  publisher = models.CharField(max_length=100)
  author = models.ForiegnKey(Autho, on_delete=models.CASCADEr)

```


Now, our **Book** class is finished. Every **Book** will have a:
* Title
* Publisher
* Author

### Class Attributes explination
* __CharField__: Ment for string
* __max\_length__: The limit for the number of characters the attribute can have
* __ForeignKey__: Creates the one-to-many relationship (Between an **Author** and a **Book**)
* __on\_delete__: Sets the deletion of the record, to delete all the records with the foreign key, to be removed

### Adding Object Information

```python
class Author(models.Model):
  first_name = models.CharField(max_length=100)
  last_name = models.CharField(max_length=100)
  city = models.CharField(max_length=100)
  state = models.CharField(max_length=100)
  country = models.CharField(max_length=100)

  def __str__(self):
    return "{} {}".format(self.last_name, self.first_name)

class Book(models.Model):
  title = models.CharField(max_length=100)
  publisher = models.CharField(max_length=100)
  author = models.ForiegnKey(Author)

  def __str__(self):
    return "{} {}".format(self.title, self.author)
```
The __str__ method, returns the specified object attributes in unicode. You can pass whichever model-class attribute you want to the method.

```python
class Author(models.Model):
  first_name = models.CharField(max_length=100)
  last_name = models.CharField(max_length=100)
  city = models.CharField(max_length=100)
  state = models.CharField(max_length=100)
  country = models.CharField(max_length=100)

  class Meta:
    ordering = ['last_name']

  def __str__(self):
    return "{} {}".format(self.last_name, self.first_name)

class Book(models.Model):
  title = models.CharField(max_length=100)
  publisher = models.CharField(max_length=100)
  author = models.ForiegnKey(Author)

  class Meta:
    ordering = ['last_name']


  def __str__(self):
    return "{} {}".format(self.title, self.author)
```

The sub-class __Meta__ allows us to order the records of the table in the desired way.

### Quick Review

We have defiend two models:
* Author
* Book
Author as 5 attributes (see above), Book has 3 attributes (see above). The major distinction between these two classes, is the **ForeignKey** attribute. By putting th **ForeignKey** in the **Book** attribute, the **PrimaryKey** is added to the **Author** model, because we passed in the model paramater.

A model is a class that is defined in the *models.py*, a model is a table in the database. Every model inherits from the parent class **Model**
