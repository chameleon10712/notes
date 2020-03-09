Lecture 13: Linking
======================

CMU - Intro to Computer Systems, Fall 2016

- `[schedule] <http://www.cs.cmu.edu/afs/cs/academic/class/15213-f16/www/schedule.html>`_

- `[video] <https://scs.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=0aef84fc-a53b-49c6-bb43-14cb2b175249>`_
- `[slide] <http://www.cs.cmu.edu/afs/cs/academic/class/15213-f16/www/lectures/13-linking.pdf>`_

|

Linker
--------

大致上是將 ``*.o files`` link 起來，並合成一個 fully linked ``executable file``

linker 會標示哪個是 entry point （程式從哪一個檔案進度、最先執行)

|

Linker 主要的工作
------------------

Step 1: symbol resolution
+++++++++++++++++++++++++++

  
- Programs ``define`` and ``reference`` symbol (global variables and functions)

::

  void swap(){...}    // define symbol swap
  swap();             // reference symbol swap
  int *p = &x;        // define symbol p, reference symbol x
  

|

- ``symbol definition`` 會在 assembly 階段就被寫在 ``symbol table`` 裡面

- 在 linking process 階段， linker 會將 ``symbol reference`` 與 ``symbol definition`` 關聯(associate)起來

- 在多個 module 的時候，可能會有 function name 重複的問題，這個時候 linker 會將正確的 reference associate 到對應的 symbol definition


|

Step 2: Relocation
++++++++++++++++++++


