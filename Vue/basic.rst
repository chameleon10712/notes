Basic Usage
==============

Computed Properties
---------------------

Basic Example

.. code:: html

  <div id="example">
    <p>Original message: "{{ message }}"</p>
    <p>Computed reversed message: "{{ reversedMessage }}"</p>
  </div>



.. code:: js

  var vm = new Vue({
    el: '#example',
    data: {
      message: 'Hello'
    },
    computed: {
      // a computed getter
      reversedMessage: function () {
        // `this` points to the vm instance
        return this.message.split('').reverse().join('')
      }
    }
  })


output

.. code::

  Orignal message: "Hello"
  Computed reverse message: "olleH"


|

Computed Caching vs Methods

- computed properties are cached based on their reactive dependencies


|

Computed vs Watched Property
-------------------------------




