Double Star / Asterisk
=========================


- `What does ** (double star/asterisk) and * (star/asterisk) do for parameters? <https://stackoverflow.com/questions/36901/what-does-double-star-asterisk-and-star-asterisk-do-for-parameters>`_


- `關於 python * 和 ** 的問題 <https://github.com/dokelung/Python-QA/blob/master/questions/star/%E9%97%9C%E6%96%BCpython*%E5%92%8C**%E7%9A%84%E5%95%8F%E9%A1%8C.md>`_


|

用於 function arguments 時
------------------------------

**unpack argument lists** when calling a function


.. code::

  lst = ['dokelung', 27, 'Taipei', 'Python']
  dic = {'name': 'dokelung', 'age': 27, 'city': 'Taipei', 'language': 'Python'}


不用 ``*`` 或 ``**`` 你可能要:

.. code::

  test(lst[0], lst[1], lst[2], lst[3])
  test(dic['name'], dic['age'], dic['city'], dic['language'])


使用 ``*`` 和 ``**``:

.. code::

  test(*lst)
  test(**dic)





StackOverflow Example
-------------------------


.. code::

  def foo(a, b, c):
      print(a, b, c)

  obj = {'b':10, 'c':'lee'}

  foo(100,**obj)
  # 100 10 lee


|

The *args will give you all function parameters as a tuple:

.. code::

  def foo(*args):
      for a in args:
          print(a)        

  foo(1)
  # 1

  foo(1,2,3)
  # 1
  # 2
  # 3

