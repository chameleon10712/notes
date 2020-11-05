Model
========



修改 DB schema

- Change your models (in ``models.py``).
- Run ``python manage.py makemigrations`` to create migrations for those changes
- Run ``python manage.py migrate`` to apply those changes to the database.

|


``on_delete`` options

- CASCADE

  - 參考 notes/db/terms

- PROTECT
- SET NULL

- `ref <https://docs.djangoproject.com/en/3.1/ref/models/fields/#django.db.models.ForeignKey.on_delete>`_



