# Django-Web-Development
Solution: RuntimeError: for those using Django4.0
I am studying the book 'Web Development with Django'.
I am in Chapter 4 and encountered a problem RuntimeError: 'reviews.apps' declares more than one default AppConfig: 'AdminConfig', 'ReviewsAdminConfig'

Here is the Solution.

admin.py
from django.contrib import admin

reviews/apps.py
from django.apps import AppConfig
class ReviewsConfig(AppConfig):
    name = "reviews"

reviews/admin.py
from django.contrib import admin

settings.py
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',

    'reviews',
]
