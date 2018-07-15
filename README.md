installation
--------------------
- requirements: install following packages via **pip** or **easy_install**
 - python 2.7
 - django 1.10
 - [django-colorfield 0.1.10](https://github.com/jaredly/django-colorfield)
 - [django-ckeditor 5.0.3](https://github.com/django-ckeditor/django-ckeditor)
- Download Django-fullpage
- Add it to your project directory
- Edit project's **settings.py**
```
 INSTALLED_APPS = [
...
    'ckeditor',
    'ckeditor_uploader',
    'colorfield',
    'fullpage.apps.FullpageConfig',
...
]

CKEDITOR_CONFIGS = {
    'awesome_ckeditor': {
        'toolbar': 'Advance',
    },
}
CKEDITOR_UPLOAD_PATH = MEDIA_ROOT + 'ck_uploads/'
CKEDITOR_RESTRICT_BY_USER = True
CKEDITOR_BROWSE_SHOW_DIRS = True
CKEDITOR_ALLOW_NONIMAGE_FILES = True
```
- <i class="icon-file"></i> Add following line to your **urlpatterns** in project's **urls.py** 
```
urlpatterns += [
    url(r'^', include('fullpage.urls')),
    url(r'^ckeditor/', include('ckeditor_uploader.urls')),
]
```
- Create models via typing following commands in terminal or cmd
```
$ python manage.py makemigrations fullpage
$ python manage.py migrate fullpage
```
- <i class="icon-refresh"></i> Run django server to see the result
```
$ python manage.py runserver
```

> **Note:**

> - Some settings are depend on your project. If you have any problem with installation of django-fullpage see our wiki or ask us.

