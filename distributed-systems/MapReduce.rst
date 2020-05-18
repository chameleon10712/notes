MapReduce
===========

`[paper] <https://pdos.csail.mit.edu/6.824/papers/mapreduce.pdf>`_


Distributed systems
----------------------

Challenges

- Concurrency
- Partial failure
- Performance


|

Infrastructure - Abstractions


- Storage

- Communication

- Computation
  
  - MapReduce

|

Implementation

- RPC, threads, concurrency control

|

Performance

- Scalability

  - 2x computers  ->  2x throughput
  - scalable speedup
  - 假設你有一個 web service, 當 user 爆炸多時, 你會想增加你的 server 數量, 但是通常你增加的 server 數量並不會正比於你的 service 服務速度。 當你從一台 server 增加為兩台 server 時，速度通常很難變成兩倍。

|

Fault Tolerance



|

MapReduce
-----------

- For big data computation

  - parallelism
  - fail tolerance
  
  |
  
  - physical
  - security / isolated





- 在處理大量資料運算時，通常可以將 computation 拆解為 ``map``, ``reduce`` 兩種 operation, 以利於進行平行運算、容錯。

|

Users specify a ``map`` function that processes a ``key/value pair`` to generate a set of ``intermediate key/value pairs``, and a ``reduce`` function that merges all intermediate values associated with the same intermediate key.


::

  map (k1,v1)           →   list(k2,v2)
  reduce (k2,list(v2))  →   list(v2)

|


- The ``intermediate values`` are supplied to the user’s reduce function via an ``iterator``. This allows us to handle lists of values that are too large to fit in memory.

- 提供給 reduce function 最為參數的 itermediate values 可以用 iterator，這樣一來就可以應付 list 數量過大超過 memory 容量的狀況


|

Example
--------

- `知乎 - 深入淺出MapReduce <https://zhuanlan.zhihu.com/p/32172999>`_



|

Terms
-------

- ``iterator``

  - 不會把所有的 ``list`` 一次 load 到 memory 裡面，而是用 ``lazy evaluation`` 的方式載入 memory (Python)
  
  - `如何更好地理解Python迭代器和生成器？ <https://www.zhihu.com/question/20829330>`_


|
Related
----------

關於 MapReduce 的討論


- `知乎 <https://www.zhihu.com/question/24280664>`_



