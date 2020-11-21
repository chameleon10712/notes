Watch
======

`JS Bin <https://jsbin.com/haxewes/1/edit?html,js,output>`_


.. code:: html

  <!DOCTYPE html>
  <html>
  <head>
    <script src="https://cdn.jsdelivr.net/npm/vue@2"></script>

    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width">
    <title>Watch Example</title>
  </head>
  <body>

    <div id="app-6">
      <p>{{ text }}</p>
      <p>{{ status }}</p>
      <input v-model="text">
    </div>


  </body>
  </html>


.. code:: js

  var app6 = new Vue({
    el: '#app-6',
    data: {
      text: 'sample text',
      status: 'None'
    },
    watch: {
      text: function(newText, oldText){
        console.log('watch');
        this.status = 'changed'
      }
    },
  })



