django-simple-skel
===========

A modern Django (1.4.x) project skeleton.

This is completely based off of Randall Degges' django-skel - https://github.com/rdegges/django-skel

My goal is to make Randall's [django-skel](https://github.com/rdegges/django-skel) more generic so it would fit a wider range of projects. For example, not all
of my projects make use of workers with Celery. If you're looking to make use of more advanced features
such as Celery task queues I would recommend starting with [django-skel](https://github.com/rdegges/django-skel) by [Randall Degges](https://github.com/rdegges).


Meta
====

* modified by: Ryan Griffin
* original author: [Randall Degges](http://rdegges.com/)


Purpose
=======

For background, see: http://rdegges.com/deploying-django

Essentially--deploying Django projects is hard. There are lots of things you
need to take into consideration. Being a Django user for years, I believe I've
found some extremely useful patterns to help manage all sorts of Django sites
(from the very smallest apps, to the largest).

This project is meant to be a boilerplate project for starting development. It
is heavily opinionated in terms of services and tools--but I think the tradeoff
is worthwhile.


Docs
====

Original project documentation is hosted at RTFD: http://django-skel.rtfd.org/.


Install
=======

django-simple-skel currently supports Django 1.4. To create a new django-skel base
project, run the following command (this assumes you have Django 1.4 installed
already):

    $ django-admin.py startproject --template=https://github.com/therg/django-simple-skel/zipball/master woot
    $ heroku config:add DJANGO_SETTINGS_MODULE=myproject.settings.prod


Where ``woot`` is the name of the project you'd like to create.

This is possible because Django 1.4's ``startproject`` command allows you to
fetch a project template over HTTP (which is what we're doing here).

While not strictly required, it is also recommended to do

     $ heroku config:add SECRET_KEY=putsomethingfairlycomplexhere

The production settings pull SECRET_KEY from environment but fallbacks
to a value which is generated mainly for development environment.

This setup allows you to easily keep your site in a public repo if you so 
wish without causing opening a route to attack your Django passwords.
