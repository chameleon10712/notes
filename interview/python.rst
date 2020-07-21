Python
===========

- `github - interview_python <https://github.com/taizilongxu/interview_python>`_
- `面試題 <https://www.jianshu.com/p/1e8b5ee9d81f>`_
- `知乎 - 110 道 Python 考題 <https://zhuanlan.zhihu.com/p/54430650>`_

|

Concept
---------




|
- Deep Copy v.s. Shallow Copy

  - Deep Copy 是將對象本身複製給另一個對象。這意味著如果對對象的副本進行更改時不會影響原對象
  - Shallow Copy 是將對象的引用複制給另一個對象。因此，如果我們在副本中進行更改，則會影響原對象

|
- 當退出Python 時是否釋放所有內存分配？
  
  - 答案是否定的。那些具有對象循環引用或者全局命名空間引用的變量，在Python 退出是往往不會被釋放; 另外不會釋放C 庫保留的部分內容。

|
- Django, Pyramid 和 Flask 之間的差異

  - Flask 是“microframework”，主要用於具有更簡單要求的小型應用程序。在 Flask 中，您必須使用外部庫。

  - Pyramid 適用於大型應用程序。它提供了靈活性，並允許開發人員為他們的項目使用正確的工具。開發人員可以選擇數據庫，URL結構，模板樣式等。

  - Django 也可以像Pyramid一樣用於更大的應用程序。

|

Functional Programming
+++++++++++++++++++++++++

- ``filter``, ``map``, ``reduce``
- `酷壳 - 函数式编程 <https://coolshell.cn/articles/10822.html>`_


map
^^^^^

.. code::

  # Add two lists using map and lambda 

  numbers1 = [1, 2, 3] 
  numbers2 = [4, 5, 6] 

  result = map(lambda x, y: x + y, numbers1, numbers2) 
  print(list(result)) 



Output: ``[5, 7, 9]``

|

Reference

- `Python map() function <https://www.geeksforgeeks.org/python-map-function/>`_


|

Lambda
++++++++

簡單來說，編程中提到的lambda表達式，通常是在 **需要一個函數，但是又不想費神去命名一個函數的場合下使用** ，也就是指 **匿名函數** 。

這一用法跟所謂λ演算（題目說明里的維基鏈接）的關係，有點像原子彈和質能方程的關係，差別其實還是挺大的。


.. code::

  map( lambda x: x*x, [y for y in range(10)] )


Reference

- `知乎 <https://www.zhihu.com/question/20125256>`_


|

|

Scope
++++++++

Python中的作用域(Scope)
^^^^^^^^^^^^^^^^^^^^^^^^

Python 中，一個變量的作用域總是由在代碼中被賦值的地方所決定的。

當Python 遇到一個變量的話他會按照這樣的順序進行搜索：

本地作用域（Local）→當前作用域被嵌入的本地作用域（Enclosing locals）→全局/模塊作用域（Global）→內置作用域（Built-in）


|

Closure
+++++++++

閉包(closure)是函數式編程的重要的語法結構。閉包也是一種組織代碼的結構，它同樣提高了代碼的可重複使用性。

當一個內嵌函數引用其外部作作用域的變量,我們就會得到一個閉包. 總結一下,創建一個閉包必須滿足以下幾點:

1. 必須有一個內嵌函數
2. 內嵌函數必須引用外部函數中的變量
3. 外部函數的返回值必須是內嵌函數


example
^^^^^^^^

.. code::

  def make_printer(msg):

      msg = "hi there"

      def printer():
          print(msg)

      return printer


  myprinter = make_printer("Hello there")
  myprinter()
  myprinter()
  myprinter()


Reference

- `Python Closure <http://zetcode.com/python/python-closures/>`_


|

GIL 
+++++

Python Global Interpreter Lock
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

線程全局鎖(Global Interpreter Lock),即Python為了保證線程安全而採取的獨立線程運行的限制,說白了就是一個核只能在同一時間運行一個線程. 對於io密集型任務，python的多線程起到作用，但對於cpu密集型任務，python的多線程幾乎佔不到任何優勢，還有可能因為爭奪資源而變慢。

解決辦法就是多進程和下面的協程(協程也只是單CPU,但是能減小切換代價提升性能)


參考

- `Python最難的問題 <https://www.oschina.net/translate/pythons-hardest-problem>`_
- `YouTube - Understanding the Python GIL <https://www.youtube.com/watch?v=Obt-vMVdM8s>`_

|

Garbage Collection
+++++++++++++++++++++

Python GC主要使用引用計數（reference counting）來跟踪和回收垃圾



|

Duck typing 
+++++++++++++
鴨子類型

|

“當看到一隻鳥走起來像鴨子、游泳起來像鴨子、叫起來也像鴨子，那麼這隻鳥就可以被稱為鴨子。”

我們並不關心對像是什麼類型，到底是不是鴨子，只關心行為。

比如在python中，有很多file-like的東西，比如 StringIO , GzipFile , socket 。它們有很多相同的方法，我們把它們當作文件使用。

又比如 list.extend() 方法中,我們並不關心它的參數是不是 list ,只要它是可迭代的,所以它的參數可以是 list / tuple / dict / 字符串 / 生成器等.

鴨子類型在動態語言中經常使用，非常靈活，使得 python 不想 java 那樣專門去弄一大堆的設計模式。




|

程式題
--------

`Reference <https://github.com/taizilongxu/interview_python#%E7%BC%96%E7%A8%8B%E9%A2%98>`_

- Fibonacci

- 矩形覆蓋

- 楊氏矩陣查找

- 去除列表中的重複元素

- 鍊錶成對調換

- 創建字典的方法



