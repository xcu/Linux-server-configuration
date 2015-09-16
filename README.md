## Linux server configuration
This document describes the features of the last project for Udacity's  Fullstack nanodegree.
# Accessing the server

The IP is 52.25.83.21, and ssh is listening on port 2200.
The application can be accessed with this URL: http://52.25.83.21.

# Software installed

* pip
* git
* apache2
* libapache2-mod-wsgi
* postgresql
* postgresql-contrib

# Plus the application specific software

* Flask (0.10.1)
* Flask-OAuth2-Login (0.0.9)
* Flask-Session (0.1.1)
* oauth (1.0.1)
* oauth2client (1.4.11)
* oauthlib (0.7.2)
* SQLAlchemy (0.8.4)
* requests (2.2.1)
* requests-oauthlib (0.4.2)
* bleach (1.4.1)

# Third party software used

* apache
* postgresql
* pip
* git
* flask 

## Files modified to configure the server
Rather than spreading the information across conf files I think it will be easier for reviewers to have it all in one place

```/etc/ssh/sshd_config```
Changed the port in which ssh listens to 2200 and removed acess for root user.

```/etc/apache2/apache2.conf```
Added a WSGIPythonPath directive to set the Python path.

```/etc/apache2/sites-enabled/000-default.conf```
Included all the information about the wsgi application so that mod_wsgi can use it.

```/var/www/catalog.wsgi```
Created this file as an entry point for mod_wsgi.

```/home/grader/.ssh/authorized_keys```
Created this file to alow passwordless acess for user grader.

```/etc/sudoers```
Modified to allow sudo without needing to type the password.

```/var/www/html/item_catalog/project.py``` and ```/var/www/html/item_catalog/item_catalog.db```
The item_catalog project uses sqllite by default. Had to modify that to connect to the new postgres DB.
