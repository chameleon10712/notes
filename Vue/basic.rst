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

Instance Lifecycle Hooks
--------------------------


Each Vue instance goes through a series of initialization steps when it’s created - for example, it needs to set up data observation, compile the template, mount the instance to the DOM, and update the DOM when data changes. Along the way, it also runs functions called **lifecycle hooks**, giving users the opportunity to add their own code at specific stages.


For example, the ``created`` hook can be used to run code after an instance is created:

.. code:: js

  new Vue({
    data: {
      a: 1
    },
    created: function () {
      // `this` points to the vm instance
      console.log('a is: ' + this.a)
    }
  })
  // => "a is: 1"


|

Life Cycle Diagram
---------------------

.. image:: https://vuejs.org/images/lifecycle.png




