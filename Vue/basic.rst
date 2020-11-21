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


