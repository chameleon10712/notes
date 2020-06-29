Destructuring Assignment
------------------------

解構賦值 (Destructuring Assignment) 是一種 JavaScript 運算式，可以將陣列或物件中的資料取出成獨立變數。


.. code-block:: javascript
  
  var a, b, rest;
  [a, b] = [10, 20];

  console.log(a);
  // expected output: 10

  console.log(b);
  // expected output: 20

  [a, b, ...rest] = [10, 20, 30, 40, 50];

  console.log(rest);
  // expected output: [30,40,50]



Object destructuring
^^^^^^^^^^^^^^^^^^^^

.. code-block:: javascript

  var o = {p: 42, q: true};
  var {p, q} = o;

  console.log(p); // 42
  console.log(q); // true


Assigning to new variable names
++++++++++++++++++++++++++++++++

.. code-block:: javascript

  var o = {p: 42, q: true};
  var {p: foo, q: bar} = o;

  console.log(foo); // 42 
  console.log(bar); // true


Default values
+++++++++++++++

.. code-block:: javascript

  var {a = 10, b = 5} = {a: 3};

  console.log(a); // 3
  console.log(b); // 5

