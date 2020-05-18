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


- Availability - 即使在有錯誤發生的情況下，仍然可以正常地進行服務

- Recoverability - 在有錯誤的情況下、也許 server 停止服務，在修理完後(after repair)可以繼續進行服務

|
- 可以使用下列方法達成 Fault Tolerance

  - Non-volatile Storage
  - Replication

|

Topic - Consistency

ex. 


假設你有一個系統支援

- 儲存 key, value pair 的 table
- put 跟 get 兩種 operation
- data replication

  - 你的 table 有兩個 (table1, table2)， table2 是 table1 的 copy


.. code:: 

  Put(K,V)
  Get(K) -> V


===  =======
  table1
------------
key   value
===  =======
1    20
===  =======

===  =======
  table2
------------
key   value
===  =======
1    20
===  =======


今天有一個 user 將其中一組 <key, value> 從原本的 ``<1, 20>`` 改為 ``<1, 21>``。
你的 server 在改完 table1 之後 crash 了， 這時就會發生 inconsistency 的狀況。



===  =======
  table1
------------
key   value
===  =======
1    21
===  =======

===  ====================
  table2
-------------------------
key   value
===  ====================
1    20   -> stale copy
===  ====================


這個時候就需要 consistency 的規則

- strong consistency
    
  - 保證 get 最近一次 put 的值是正確的
  - All accesses are seen by all parallel processes (or nodes, processors, etc.) in the same order (sequentially)


- weak consistency

  - 在一定時間內，不保證 get 到最近一次 put 的新值


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



