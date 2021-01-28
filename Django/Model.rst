Model
========



修改 DB schema
---------------

- Change your models (in ``models.py``).

- Run

  .. code:: sh

    python manage.py makemigrations
    
    # to create migrations for those changes

  
- Run  

  .. code:: sh
  
    python manage.py migrate
    
    # to apply those changes to the database.

|

Clear / Flush DB all objects
--------------------------------

.. code:: sh

  python manage.py flush

|

DB options
-------------

``on_delete`` options

- CASCADE

  - 參考 notes/db/terms

- PROTECT
- SET NULL

- `ref <https://docs.djangoproject.com/en/3.1/ref/models/fields/#django.db.models.ForeignKey.on_delete>`_



|


Model.__str__()
------------------

標示該 obj 的 info detail

.. code:: py

  from django.db import models

  class Person(models.Model):
      first_name = models.CharField(max_length=50)
      last_name = models.CharField(max_length=50)

      def __str__(self):
          return '%s %s' % (self.first_name, self.last_name)



|

Validating objects
---------------------


There are three steps involved in validating a model:

- Validate the model fields - ``Model.clean_fields()``
- Validate the model as a whole - ``Model.clean()``
- Validate the field uniqueness - ``Model.validate_unique()``


All three steps are performed when you call a model’s ``full_clean()`` method.


- `ref <https://docs.djangoproject.com/en/3.1/ref/models/instances/#validating-objects>`_



|


Serializing Django objects
----------------------------

- XML
- JSON
- YAML



- `Django Document <https://docs.djangoproject.com/en/3.1/topics/serialization/>`_

.. code:: py

  from django.core import serializers
  data = serializers.serialize("xml", SomeModel.objects.all())

