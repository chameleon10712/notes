MapReduce
===========


Users specify a ``map`` function that processes a ``key/value pair`` to generate a set of ``intermediate key/value pairs``, and a ``reduce`` function that merges all intermediate values associated with the same intermediate key.


::

  map (k1,v1)           →   list(k2,v2)
  reduce (k2,list(v2))  →   list(v2)
