Shorthands
=============


``v-bind`` Shorthand

.. code:: html

  <!-- full syntax -->
  <a v-bind:href="url"> ... </a>

  <!-- shorthand -->
  <a :href="url"> ... </a>

  <!-- shorthand with dynamic argument (2.6.0+) -->
  <a :[key]="url"> ... </a>



``v-on`` Shorthand

.. code:: html

  <!-- full syntax -->
  <a v-on:click="doSomething"> ... </a>

  <!-- shorthand -->
  <a @click="doSomething"> ... </a>

  <!-- shorthand with dynamic argument (2.6.0+) -->
  <a @[event]="doSomething"> ... </a>



