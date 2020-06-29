Arrow Function
=================

reference

- `MDN <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions>`_

|

No separate this
------------------

An arrow function does not have its own ``this``.
The ``this`` value of the enclosing lexical scope is used; 
arrow functions follow the normal variable lookup rules. 
So while searching for ``this`` which is not present in the current scope, 
an arrow function ends up finding the ``this`` from its enclosing scope.


Thus, in the following code, 
the ``this`` within the function that is passed to setInterval has the same value as the this in the lexically enclosing function:

.. code:: js

  function Person(){
    this.age = 0;

    setInterval(() => {
      this.age++; // |this| properly refers to the Person object
    }, 1000);
  }

  var p = new Person();

|


Function body
---------------


concise body

.. code:: javascript

  var func = x => x * x;                  
  // concise body syntax, implied "return"


block body

.. code:: javascript

  var func = (x, y) => { return x + y; }; 
  // with block body, explicit "return" needed
  Returning object literals







