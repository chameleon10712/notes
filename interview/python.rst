Python
===========

- `github - interview_python <https://github.com/taizilongxu/interview_python>`_
- `面試題 <https://www.jianshu.com/p/1e8b5ee9d81f>`_

|

Concept
---------


- Lambda

|

- Functional Programming
  
  - ``filter``, ``map``, ``reduce``
  - `酷壳 - 函数式编程 <https://coolshell.cn/articles/10822.html>`_

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

Closure
+++++++++

example

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


線程全局鎖(Global Interpreter Lock),即Python為了保證線程安全而採取的獨立線程運行的限制,說白了就是一個核只能在同一時間運行一個線程. 對於io密集型任務，python的多線程起到作用，但對於cpu密集型任務，python的多線程幾乎佔不到任何優勢，還有可能因為爭奪資源而變慢。

解決辦法就是多進程和下面的協程(協程也只是單CPU,但是能減小切換代價提升性能)


參考

- `Python最難的問題 <https://www.oschina.net/translate/pythons-hardest-problem>`

|

Garbage Collection
+++++++++++++++++++++

Python GC主要使用引用計數（reference counting）來跟踪和回收垃圾



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



