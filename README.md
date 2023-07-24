# Django Polls App
Polls is a Django app to conduct web-based polls. For each question, visitors can choose between a fixed number of answers.

The **polls** directory can be copied into a new Django project and be immediately used. It is not quite ready to be published though. For that, we need to make sure the app gets installed correctly.

## Quick Start
1. Add "polls" directory into you django project folder, like this:
mysite/
    manage.py
    mysite/
        __init__.py
        settings.py
        urls.py
        asgi.py
        wsgi.py
    **polls/**
        __init.py__
        admin.py
        migrations/
            ...
        models.py
        static/
            ...
        templates/
            ...
        tests.py
        urls.py
        views.py

2. Add "polls" app to your INSTALLED_APPS settings, open **mysite/settings.py**.
    ```python
    ...

    INSTALLED_APPS = [
        ...,
        "polls.apps.PollsConfig",  # new
    ]

    ```

3. Include the polls URLconf in your project urls.py like this:
    ```python
    from django.contrib import admin
    from django.urls import include, path

    urlpatterns = [
        path("polls/", include("polls.urls")),  # new
        path("admin/", admin.site.urls),
    ]
    ```

4. Open up **mysite/settings.py** again, and configure your database setting. By default, the configuration uses SQLite.


5. Run ```python3 manage.py makemigrations polls``` and on success run ```python3 manage.py migrate``` to create the polls models.


6. Start the development server and visit http://127.0.0.1:8000/admin/ to create a poll (you'll need the Admin app enabled with a user/superuser).

5. Visit http://127.0.0.1:800/polls/ to participate in the poll.

