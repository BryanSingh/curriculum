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

### Settings.py
Before we create our first app for our project, we need to add out newly created app to the __settings.py__ file.  This file contains all of the semantics of our Django application. Look for the section called **INSTALLED__APPS**, this is how we can include other libraries inside of our project (If you are familiar with Rails, this is similar to a Gemfile.)

Every time we create a new app for a project, you will need to add the app name to the *settings.py* file. Your newly edited *settings.py* file should look something like this.

~ python
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'bookshelf'
]



