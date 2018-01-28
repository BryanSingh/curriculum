
part\_four
## Lets start adding some meat to our app

### Creating our model

#### What are Models?
Recall from the earlier section, when we talked about **MVC** (model, view, controller).

The Model is how the app talks to the database. In this case our database will be sqlite3. Note, when you deploy your app to production, is is wise to use another persistent data system, relational or non-relator (PostgreSQL, MongoDB, MySQL, etc …)

A database consists of tables, tables correlate to app model classes. Every newly created is a child of the parent class, Model.

``` python
from django.db import models
```

Lets create our for table (class). Since our first app is our bookshelf, a way to display the contents of our system. We need to define two new classes, a **Book** class and a ** Author** class. Where every author has many books (a one-to-many) relationship.


Here, we create the bare bone layout of our models.

``` python
from django.db import models

  class Book(models.Model):
pass

  class Author(models.Model):
pass
```

We will first create the Author model.

```python
from django.db import models

  class Book(models.Model):
pass

  class Author(models.Model):
first_name = models.CharField(max_length=100)
last_name = models.CharField(max_length=100)
city = models.CharField(max_length=100)
state = models.CharField(max_length=100)
country = models.CharField(max_length=100)
```
