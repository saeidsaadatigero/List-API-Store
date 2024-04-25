## Shopping-List-API
saeidsaadatigero@gmail.com
- A sample shoping list API with Postgresql database.
- I learned and use API of this project
## Features
The goal of this project is to provide a uniform API for both web and mobile frontend shopping list applications.
With this API;
- You can create a user account - Registration
- You can login and log out - Authorization and Authentication
- You can create, view, update, and delete a shopping list in your user account
- You can create, view, update, and delete an item in your shopping list under your account

## Technology stack
Tools used during the development of this API are;
- [Swagger](https://swagger.io/) - this is a tool for documenting the API
- [JWT](https://jwt.io) - JWT is an open standard (RFC 7519) that defines a compact and self-contained way for securely transmitting information between parties as a JSON object
- [Django](https://www.djangoproject.com) - a python web framework
- [Django REST Framework](http://www.django-rest-framework.org) - a flexible toolkit to build web APIs
- [Postgresql](https://www.postgresql.org/) - this is a database server
## Requirements
- Use Python 3.x.x+
- Use Django 2.x.x+
## Tests
> python manage.py test
## Running the application
To run this application, clone the repository on your local machine and execute the following command.
```sh
    $ cd drf_shopping_list_api
    $ virtualenv virtenv
    $ source virtenv/bin/activate
    $ pip install -r requirements.txt
    $ python manage.py makemigrations
    $ python manage.py migrate
    $ nohup python manage.py runserver & disown
```
## Base URL for the API
The base url for this api is https://drf-api-shopping-list.herokuapp.com/ in case you want to try out this API endpoints
using curl or postman from your computer with out cloning this repository. For example, on linux commandline issue this
curl command to login (you will need to first register to login, please see documentation).
```
curl -H "Content-Type: application/json" -X POST -d '{"username":"foo@bar.com","password":"foobar"}' https://drf-api-shopping-list.herokuapp.com/auth/login/
```
#### Endpoints to create a user account and login into the application
HTTP Method|End point | Public Access|Action
-----------|----------|--------------|------
POST | /auth/register | True | Create an account
POST | /auth/login | True | Login a user
POST | /auth/logout | False | Logout a user
POST | /auth/reset-password | False | Reset a user password
GET | /user | False | Returns details of a logged in user
PUT | /user | False | Updates details of a logged in user

#### Endpoints to create, update, view and delete a shopping list
HTTP Method|End point | Public Access|Action
-----------|----------|--------------|------
POST | /shoppinglists | False | Create a shopping list
GET | /shoppinglists | False | View all shopping lists
GET | /shoppinglists/search/ | False | View all shopping lists
GET | /shoppinglists/id | False | View details of a shopping list
PUT | /shoppinglists/id | False | Updates a shopping list with a given id
DELETE | /shoppinglists/id | False | Deletes a shopping list with a given id

#### Endpoints to create, update, view and delete a shopping list item
HTTP Method|End point | Public Access|Action
-----------|----------|--------------|------
GET | /shoppinglists/id/items | False | View Items of a given list id
GET | /shoppinglists/id/items/<item_id> | False | View details of a particular item on a given list id
GET | /shoppinglists//items/search/ | False | View details of a particular item on a given list id
POST | /shoppinglists/id/items | False | Add an Item to a shopping list
PUT | /shoppinglists/id/items/<item_id> | False | Update a shopping list item on a given list
DELETE | /shoppinglists/id/items/<item_id> | False | Delete a shopping list item from a given list
