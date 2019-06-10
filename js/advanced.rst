
bind()
======

.. code-block:: javascript

  var module = {
    x: 42,
    getX: function() {
      return this.x;
    }
  }

  var unboundGetX = module.getX;
  console.log(unboundGetX()); // The function gets invoked at the global scope
  // expected output: undefined

  var boundGetX = unboundGetX.bind(module);
  console.log(boundGetX());
  // expected output: 42


`[MDN] <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_objects/Function/bind>`_





