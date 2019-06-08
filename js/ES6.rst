ES6
===

Destructuring Assignment
------------------------


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




Const
-----

Constants (常數) 有點像使用 ``let`` 所宣告的變數，具有區塊可視範圍。常數不能重複指定值，也不能重複宣告。

.. code-block:: javascript

  const number = 42;

  try {
    number = 99;
  } catch(err) {
    console.log(err);
    // expected output: TypeError: invalid assignment to const `number'
    // Note - error messages will vary depending on browser
  }

  console.log(number);
  // expected output: 42




