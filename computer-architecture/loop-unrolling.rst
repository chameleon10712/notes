Loop Unrolling
=================


.. code:: py

  for(i=0;i<1000;i++){
    x[i] = x[i] + s
  }


unroll loop

.. code:: py

   for(i=0;i<1000;i+=4){
      x[i] = x[i] + s;
      x[i+1] = x[i+1] + s;
      x[i+2] = x[i+2] + s;
      x[i+3] = x[i+3] + s;
   }







