## How a Django App is structured

### Project vs App
In Django, you have a project and an app. The 'project' is the overall site you are making, while an 'app' is a feature of the project/site.
* _Example_:
	* Project: Book Store
		* App: Bookshelf
		* App: Payment System


### Creating your Project
```bash
$ django-admin startproject bookstore && cd bookstore
```

#### What you got
When you go into the newly created directory, you see more of Django in action.
```bash
.
├── bookstore
├── manage.py
├── bookstore
|   ├── __init__.py
|   └── settings.py
|   └── urls.py
|   └── wsgi.py
```

On completion of the python script, you get a new directory called bookstore, don't worry, this is not an error. You also have a python file called _manage.py_. We will dive in deeper into this file later. A majority of the work you will be doing will have to be done with _manage.py_.

```bash
$ cd bookstore
```


### Create your first app
```bash
$ python manage.py startapp bookshelf
```

```bash
.
├── bookstore
├── manage.py
├── bookstore
|   ├── __init__.py
|   └── settings.py
|   └── urls.py
|   └── wsgi.py
├── bookshelf
|   ├── __init__.py
|   ├── admin.py
|   ├── apps.py
```