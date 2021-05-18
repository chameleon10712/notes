Dependences and Hazards
==========================

WAW harzard

.. code:: py

  I: B = 3
  K: A = B + 1
  J: B = 7 # output dependence
  

Name dependence

- can also be removed by renaming

.. code:: py

  I: B1 = 3
  K: A = B1 + 1
  J: B = 7
  

