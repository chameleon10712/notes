Python
===========

- `GitHub - interview_python <https://github.com/taizilongxu/interview_python>`_
- `GitHub - python interview questions <https://github.com/kenwoodjw/python_interview_question>`_  
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
- `Closure - Javascript | MDN <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures>`_


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

Python 2 v.s. Python 3
+++++++++++++++++++++++++

1、Python3 使用 print 必須要以小括號包裹打印內容，比如 ``print('hi')``。 Python2 既可以使用帶小括號的方式，也可以使用一個空格來分隔打印內容，比如 ``print 'hi'``

2、python2 ``range(1,10)`` 返回列表，python3 中返回迭代器，節約內存

3、python2 中使用 ascii 編碼， python 中使用 utf-8 編碼

4、python2 中 unicode 表示字符串序列， str 表示字節序列。 Python3中 str 表示字符串序列， byte 表示字節序列

5、python2 中為正常顯示中文，引入 coding 聲明， python3 中不需要

6、python2 中是 ``raw_input()`` 函數，python3 中是 ``input()`` 函數


Reference

- `Python 2.7.x與Python 3.x的主要差異 <http://chenqx.github.io/2014/11/10/Key-differences-between-Python-2-7-x-and-Python-3-x/>`_

|

Class Objects
+++++++++++++++++

Class objects support two kinds of operations: ``attribute references`` and ``instantiation``.


Attribute references
^^^^^^^^^^^^^^^^^^^^^^

.. code:: python

  class MyClass:
      """A simple example class"""
      i = 12345

      def f(self):
          return 'hello world'

|

- ``MyClass.i`` and ``MyClass.f`` are valid attribute references
- ``__doc__`` is also a valid attribute, returning the docstring belonging to the class: ``"A simple example class"``


Class instantiation
^^^^^^^^^^^^^^^^^^^^^^

一般初始化

.. code:: py

  x = MyClass()



客製化初始值


.. code:: python

  def __init__(self):
      self.data = []


.. code:: py

  >>> class Complex:
  ...     def __init__(self, realpart, imagpart):
  ...         self.r = realpart
  ...         self.i = imagpart
  ...
  >>> x = Complex(3.0, -4.5)
  >>> x.r, x.i
  (3.0, -4.5)

|

Reference

- `Python Tutorial <https://docs.python.org/3/tutorial/classes.html#class-objects>`_



|


Class Variables vs. Instance Variables
+++++++++++++++++++++++++++++++++++++++++

類變量(class variables)  和 實例變量(instance variables)

Generally speaking, instance variables are for data unique to each instance and class variables are for attributes and methods shared by all instances of the class


通常來說，實例變量(instance variables)是對於每個實例(instance)都獨有的數據，而類變量(class variables)是該類(class)所有實例共享的屬性和方法


.. code:: python

  class Dog:

      kind = 'canine'         
      # class variable shared by all instances
      # 類屬性 kind 為所有實例所共享

      def __init__(self, name):
          self.name = name    
          # instance variable unique to each instance
          # 實例屬性name為每個Dog的實例獨有

  >>> d = Dog('Fido')
  >>> e = Dog('Buddy')
  >>> d.kind                  # shared by all dogs
  'canine'
  >>> e.kind                  # shared by all dogs
  'canine'
  >>> d.name                  # unique to d
  'Fido'
  >>> e.name                  # unique to e
  'Buddy'




|

Reference

- `Python Tutorial <https://docs.python.org/3/tutorial/classes.html#class-and-instance-variables>`_



|

Import 用法
+++++++++++++


Reference

- `知乎 - Python中import的用法 <https://zhuanlan.zhihu.com/p/63143493>`_
- `GeeksforGeeks <https://www.geeksforgeeks.org/import-module-python/>`_


|

Decorator
+++++++++++





|

@staticmethod 和 @classmethod
++++++++++++++++++++++++++++++++++





Reference

- `GitHub - interview_python <https://github.com/taizilongxu/interview_python#3-staticmethod%E5%92%8Cclassmethod>`_


|

Dictionary Comprehension 字典推導式
++++++++++++++++++++++++++++++++++++++


.. code:: python

  d  = { key : value  for ( key , value ) in  iterable }


Reference

- `Python Dictionary Comprehension <https://www.geeksforgeeks.org/python-dictionary-comprehension/>`_


|


Python 中單下劃線和雙下劃線
+++++++++++++++++++++++++++++



Reference

- `Naming with Underscores in Python <https://medium.com/python-features/naming-conventions-with-underscores-in-python-791251ac7097>`_ 



|

Mutable vs Immutable Objects
++++++++++++++++++++++++++++++

可更改（mutable）與 不可更改（immutable）對象


在 python 中，``strings``, ``tuples``, 和 ``numbers`` 是不可更改的對象（immutable objects），而 ``list`` , ``dict``, ``set`` 等則是可以修改的對象（mutable objects）






|


Iterator v.s. Generator
+++++++++++++++++++++++++++

迭代器和生成器

Reference

- `StackOverflow <https://stackoverflow.com/questions/231767/what-does-the-yield-keyword-do>`_
- `python practice book <https://anandology.com/python-practice-book/iterators.html>`_


|

Object introspection
+++++++++++++++++++++++



``introspection`` is the ability to determine the type of an object at runtime.

|

這個也是python彪悍的特性.

自省就是面向對象的語言所寫的程序在運行時,所能知道對象的類型.簡單一句就是運行時能夠獲得對象的類型.比如 ``type()``, ``dir()``, ``getattr()``, ``hasattr()``, ``isinstance ()``


- ``dir``

.. code:: py

  my_list = [1, 2, 3]
  dir(my_list)
  # Output: ['__add__', '__class__', '__contains__', '__delattr__', '__delitem__',
  # '__delslice__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__',
  # '__getitem__', '__getslice__', '__gt__', '__hash__', '__iadd__', '__imul__',
  # '__init__', '__iter__', '__le__', '__len__', '__lt__', '__mul__', '__ne__',
  # '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__reversed__', '__rmul__',
  # '__setattr__', '__setitem__', '__setslice__', '__sizeof__', '__str__',
  # '__subclasshook__', 'append', 'count', 'extend', 'index', 'insert', 'pop',
  # 'remove', 'reverse', 'sort']


- ``type`` and ``id``

.. code:: py

  print(type(''))
  # Output: <type 'str'>

  print(type([]))
  # Output: <type 'list'>

  print(type({}))
  # Output: <type 'dict'>

  print(type(dict))
  # Output: <type 'type'>

  print(type(3))
  # Output: <type 'int'>


.. code:: py

  name = "Yasoob"
  print(id(name))
  # Output: 139972439030304



|

__new__和__init__的區別
+++++++++++++++++++++++++

- __new__是一個靜態方法,而__init__是一個實例方法.
- __new__方法會返回一個創建的實例,而__init__什麼都不返回.
- 只有在__new__返回一個cls的實例時後面的__init__才能被調用.
- 當創建一個新實例時調用__new__,初始化一個實例時用__init__



Reference

- `GitHub <https://github.com/taizilongxu/interview_python#15-__new__%E5%92%8C__init__%E7%9A%84%E5%8C%BA%E5%88%AB>`_


|

其他
+++++

- Python function overloading

  - `知乎 為什麼Python 不支持函數重載？而其他語言大都支持？ <https://www.zhihu.com/question/20053359>`_
  - `StackOverflow <https://stackoverflow.com/questions/6434482/python-function-overloading>`_







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



