MapReduce
===========

`[paper] <https://pdos.csail.mit.edu/6.824/papers/mapreduce.pdf>`_

|

在處理大量資料運算時，通常可以將 computation 拆解為 ``map``, ``reduce`` 兩種 operation, 以利於進行平行運算、容錯。

Pros

- parallelize large computation easily
- use re-execution as the primary mechanism for fault tolerance

|

Users specify a ``map`` function that processes a ``key/value pair`` to generate a set of ``intermediate key/value pairs``, and a ``reduce`` function that merges all intermediate values associated with the same intermediate key.


::

  map (k1,v1)           →   list(k2,v2)
  reduce (k2,list(v2))  →   list(v2)
