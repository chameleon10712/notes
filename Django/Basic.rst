Basic Usage
===============

Start a Project
-----------------

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




Create app
-------------

.. code::

  $ python manage.py startapp polls


結構

.. code::
  
  polls/
    __init__.py
    admin.py
    apps.py
    migrations/
        __init__.py
    models.py
    tests.py
    views.py


--

啟動 Server
--------------

.. code::

  python manage.py runserver


shell

.. code::

  python manage.py shell







