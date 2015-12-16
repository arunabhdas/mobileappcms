mobileappcms
============

The steps here were followed for bootstrapping the project :

https://www.jeffknupp.com/blog/2012/02/09/starting-a-django-project-the-right-way/

Steps
-----

Create project as follows 
django-admin.py startproject mobileappcms

Add heroku as remote as follows
heroku git:remote -a mobileappcms

Add polls as follows 
python manage.py startapp polls

* Configure urls.py in polls

polls/urls.py
from django.conf.urls import url

from . import views

urlpatterns = [
    url(r'^$', views.index, name='index'),
]

* Configure urls.py in mobileappcms

from django.conf.urls import include, url
from django.contrib import admin

urlpatterns = [
    url(r'^polls/', include('polls.urls')),
    url(r'^admin/', admin.site.urls),
]
