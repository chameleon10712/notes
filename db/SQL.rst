SQL
=====


Set Operation
---------------

- union

.. code-block:: python

  (select course_id from section where semester = ’Fall’ and year= 2009)
  union 
  (select course_id from section where semester = ’Spring’ and year= 2010);


- intersect
- except


Nested Subqueries
-------------------



Aggregate functions
---------------------

• Average:``avg``
• Minimum:``min``
• Maximum:``max``
• Total:``sum``
• Count:``count``

|


- group by

- having



