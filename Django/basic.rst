Basic Usage
===============

shell

.. code::

  python manage.py shell



|

修改 DB schema

- Change your models (in ``models.py``).
- Run ``python manage.py makemigrations`` to create migrations for those changes
- Run ``python manage.py migrate`` to apply those changes to the database.



