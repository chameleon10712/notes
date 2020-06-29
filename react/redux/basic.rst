Redux
========

Pure function

- function depends only on the input variable


Impure function

- functions depends not only on the input variable


|

.. code:: javascript
  
  // Pure Function
  function square(x) {
    return x*x;
  }
  function squareAll(items) {
    return items.map(square);
  }
  
  // Impure Function
  function sqaure(x) {
    updateXInDatabase(x);
    return x*x;
  }
  
  function squareAll(items) {
    for(let i=0; i< items.length; i++) {
      items[i] = square(items[i]);
    }
  }








