Memory Consistency
=====================



Sequential Consistency
------------------------

Process 0

.. code::
  
  A = 1          (a)
  Ready = 1      (b)


Process 1

.. code::

  x = Reay      (c)
  y = A         (d)


Possible outcome for (x,y):

- (0,0), (0,1), (1,1)


不會出現 (1,0) 的理由 - 因為 (1,0) 不符合 Process 1 的 program order 










