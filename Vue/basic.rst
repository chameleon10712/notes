Vue
======

Every Vue application starts by creating a new **Vue instance** with the ``Vue`` function:

.. code:: js

  var vm = new Vue({
    // options
  })




A Vue application consists of a **root Vue instance** created with ``new Vue``, 
optionally organized into a tree of nested, reusable components. For example, a todo app’s component tree might look like this:


.. code::

  Root Instance
  └─ TodoList
     ├─ TodoItem
     │  ├─ TodoButtonDelete
     │  └─ TodoButtonEdit
     └─ TodoListFooter
        ├─ TodosButtonClear
        └─ TodoListStatistics



Data and Methods
------------------

reactivity system


.. code:: js

  // Our data object
  var data = { a: 1 }

  // The object is added to a Vue instance
  var vm = new Vue({
    data: data
  })

  // Getting the property on the instance
  // returns the one from the original data
  vm.a == data.a // => true

  // Setting the property on the instance
  // also affects the original data
  vm.a = 2
  data.a // => 2

  // ... and vice-versa
  data.a = 3
  vm.a // => 3


|

Life Cycle Diagram
---------------------

.. image:: https://vuejs.org/images/lifecycle.png




