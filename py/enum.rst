Enum
======

- `Python Document <https://docs.python.org/3/library/enum.html>`_


.. code:: py

  from enum import Enum
  class Color(Enum):
       RED = 1
       GREEN = 2
       BLUE = 3
  
  print(Color.RED)
  # Color.RED
  
  print(repr(Color.RED))
  # <Color.RED: 1>
  
  print(Color.RED.name)
  # RED
  

