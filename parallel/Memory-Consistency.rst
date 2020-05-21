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

  x = Ready     (c)
  y = A         (d)


- All locations are initialized to 0

- Possible outcome for (x,y):

  - (0,0), (0,1), (1,1)
  |

  - 不會出現 (1,0) 的理由: 因為 (1,0) 不符合 Process 0 的 program order , 以 Process 0 的角度來看, Ready = 1 的時候(b), (a) 必然已經執行, 所以不可能










