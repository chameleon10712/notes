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

Step1: ``symbol resolution``

  
- Programs ``define`` and ``reference`` symbol (global variables and functions)
  
  |

  - ``void swap(){ ... }`` 這個動作叫做 define symbol
  
  - ``swap()`` 這個叫做 reference symbol
  
  - ``int *p = &x`` 定義 symbol p, reference x

|

- symbol resolution 主要是將 ``symbol reference`` 與 ``symbol definition`` 關聯(associate)起來

