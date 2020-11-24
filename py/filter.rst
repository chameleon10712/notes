Filter 
========

`How to filter a dictionary according to an arbitrary condition function? <https://stackoverflow.com/a/16589453>`_


.. code:: py

  points={'a':(3,4), 'b':(1,2), 'c':(5,5), 'd':(3,3)}


sol.

.. code:: py

  {k: v for k, v in points.items() if v[0] < 5 and v[1] < 5}


`python filter list of dictionaries based on key value <https://stackoverflow.com/a/29051598>`_




