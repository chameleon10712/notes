Closures
===========


`[MDN] Closures <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures>`_



A ``closure`` is the combination of a function bundled together (enclosed) with references to its surrounding state (the ``lexical environment``). 
In other words, a closure gives you access to an outer function’s scope from an inner function. 
In JavaScript, closures are created every time a function is created, at function creation time.

|

Lexical scoping
-------------------

.. code:: js

  function init() {
    var name = 'Mozilla'; // name is a local variable created by init
    function displayName() { // displayName() is the inner function, a closure
      alert(name); // use variable declared in the parent function
    }
    displayName();
  }
  init();


