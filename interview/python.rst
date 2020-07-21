Python
===========

- `github - interview_python <https://github.com/taizilongxu/interview_python>`_
- `面試題 <https://www.jianshu.com/p/1e8b5ee9d81f>`_

|

- Closure
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

程式題
--------

`Reference <https://github.com/taizilongxu/interview_python#%E7%BC%96%E7%A8%8B%E9%A2%98>`_

- Fibonacci

- 矩形覆蓋

- 楊氏矩陣查找

- 去除列表中的重複元素

- 鍊錶成對調換

- 創建字典的方法



