Command
============

.. code:: shell

  gcc -o hello -Wall -g hello.c

  # 去除掉 debug symbol 及 移掉其他不需要的東西
  strip hello



.. code:: shell

  make hello
  nm hello
  
  cp hello hello1

  gcc -c hello.c
  
  # nm - list symbols from object files 
  # 看obj code 裡面有什麼 symbol
  
  nm hello.o
  
  gcc hello.o -o hello
  nm hello

  ls -al hello hello1 hello.o
  
  # strip 移除掉給使用者看得額外資訊
  strip hello
  # strip 後沒有東西
  nm hello
  
  # -D 還是可以看出一點
  nm -D hello
  
  
  
  
|
  
GDB
=====

.. code:: shell

  gdb hello
  gdb >> list


