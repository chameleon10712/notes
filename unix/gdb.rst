Command
============

.. code::

  gcc -o hello -Wall -g hello.c

  # 去除掉 debug symbol 及 移掉其他不需要的東西
  strip hello



.. code::

  make hello
  nm hello

  gcc -c hello.c
  
  # nm - list symbols from object files 
  # 看obj code 裡面有什麼 symbol
  
  nm hello.o
  
  gcc hello.o -o hello

  nm hello



