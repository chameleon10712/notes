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

.. image:: https://i.imgur.com/bNwJeeT.png


- `slideshare <https://www.slideshare.net/jserv/how-a-compiler-works-gnu-toolchain>`_

|

Static Linking
------------------

``*.c`` ---[ Translator (cpp, cc1, as) ]-->  ``*.o``  ----[ Linker (ld) ]--->  ``executable file``

- ``gcc`` 會呼叫一系列 translator, 首先會先呼叫 c preprocessor ``cpp``, 然後再呼叫 c 的 compiler ``cc1``, compiler 會產生 assembly code 後傳給 assembler, assembler 會將 assembly code 再 translate 成 ``.o`` file

- ``.c file`` 在這裡稱為 ``source file``
- ``.o file`` 稱為 ``relocatable object file``, 因為他們還可以被整合在一起
- 最後 output 的 file 被稱為 ``fully linked executable file``

|

三種 Object Files
----------------------

- relocatable object file (.o file)

  - 也是 binary file, 但格式是給 linker 用的

- executable object file (a.out)


- shared object file (.so file)

|
- 這三種 object files 都用同一種 format - Executable and Linkable Format (ELF)


Executable and Linkable Format (ELF)
---------------------------------------

- object files 的 standard format
- generic name: ``ELF binaries``

|

- ``.data`` : code section
- ``.bss``

|


Linker Symbols
----------------

- Global symbols
- External symbols
- Local symbols



|


What do linkers do? 
-----------------------------

Step 1: symbol resolution
+++++++++++++++++++++++++++

  
- Programs ``define`` and ``reference`` symbol (``global variables`` and ``functions``)

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

- 將多個 code & data section merge 成單一的 section
- relocate symbol，將 symbol 與實際的記憶體位置 bind 在一起，然後查看該 symbol 的 references 、將這些 references 指到實際的記憶體位置 (update the reference so that it point to the right spot)


|

More
====================

Symbol Resolution
-------------------

Linker Symbols
+++++++++++++++++

- linker 只會管 global variable 以及 function，並不會處理 local variable

  - C functons and global variables defined with the ``static`` attribute.	
  - local variable 由 compiler 處理

|

Local Symbols
+++++++++++++++++

::

  int f()
  {
    static int x = 0;  // local static C variable, 這裡的 x 只會被 f() 看到
    return x;
  }

  int g()
  {
    static int x = 1; // local static C variable, 這裡的 x 只會被 g() 看到
    return x;
  }
  
  // 在這個例子裡面兩個 x 都不是存在 ``stack`` 而是存在 ``.data``
  // compiler 對這兩個 x 會給予不同的 symbol 、並且分配不同的空間給他們（並不會混在一起)

- local static C variable: stored in either ``.bss`` or ``.data``




|

Relocation
------------

