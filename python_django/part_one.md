# Part One
## Lets Begin!

## What is Django?
Django is a framework for the programming language Python (Similar to Ruby on Rails for the language Ruby). Django is a very popular web building tool and is used by many companies; some are but not limited to:
* JOOR
* NASA (website)
* Bitbucket (GitHub Alternative)
* Instagram (Browser Version)

Development done in Django is very rapid and overal fun to work with! It uses a design pattern called **M**odel **V**iew **C**ontroller, or more specifclly **M**odel **V**iew **T**emplate (more on this later!)

### MVC
Let's take a second to define a couple terms that are important to Django and programming!
* Design Patterns - Just a fancy phrase to describe how your application is layed out. Not every website, software application, mobile application, etc ... is build using the same design pattern. Django is built around the design patter, **M**odel **V**iew **C**ontroller.
	* **M**odel: How you web application talks to it's database.
		* _Example_: For the book store, you will want users to create a book of which they can sell.
		* _Explination_: The books that each user adds is stored in a database which is connected to your Model. The model will be the liaison between database and the controller.
	* **C**ontroller: What you webapp users are able to see.
		* _Example_: You want every user to see their books, and see the possible books they can buy.
		* _Explination_: The controller talks to the model and gathers the information on what the user can see, based on where they are in the site.
	* **V**iew: What your users actuall see.
		* _Example_: A user wants to see his bookself (their own books)
		* _Explination_: The controller talks to the model to get all of the users books, and then the controler passes that information to te view for the user to see.

### MVT