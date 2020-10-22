Basic Usage
===============

Start a Project

.. code::

  django-admin startproject mysite


- avoid names like ``django`` or ``test``


結構

.. code::

  mysite/
      manage.py
      mysite/
          __init__.py
          settings.py
          urls.py
          asgi.py
          wsgi.py



--

啟動 Server

.. code::

  python manage.py runserver


shell

.. code::

  python manage.py shell



|

修改 DB schema

- Change your models (in ``models.py``).
- Run ``python manage.py makemigrations`` to create migrations for those changes
- Run ``python manage.py migrate`` to apply those changes to the database.



