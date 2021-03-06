Lecture 3: GFS
=================

MIT - 6.824 Distributed Systems, Spring 2020

- `[Schedule] <https://pdos.csail.mit.edu/6.824/schedule.html>`_
- `[Video] <https://www.youtube.com/watch?v=EpIgvowZr00&feature=emb_logo>`_
- `[Notes] <https://pdos.csail.mit.edu/6.824/notes/l-gfs.txt>`_
- `[FAQ] <https://pdos.csail.mit.edu/6.824/papers/gfs-faq.txt>`_
- `[Paper] <https://pdos.csail.mit.edu/6.824/papers/gfs.pdf>`_

|



Big Storage System
---------------------

WHY HARD?

- Performance -> Sharding

- Faults -> Tolerance

- Tolerance -> Replication

- Replication -> Inconsistency

- Consistency -> Low Performance

--

Strong Consistency


Bad Replication Design



|

GFS
=======

Goal

- Big, fast
- Global
- Sharding
- Automatic recovery


Feature

- Single data center
- Internal use
- Big sequential (not random) access

|


Single Master
----------------

(v): volatile  (nv): nonvolatile


Master Data
+++++++++++++

- filename

  - array of chunck handles (nv)


- chunck handle

  - list of chunck servers (v)
  - version # (nv)
  - primary (v)
  - lease expiration (v)


- ``log``, ``checkpoint`` -> Disk


Operation
+++++++++++


READ

1. Client send name, offset -> Master

2. Master send Chunck Handle, list of Chunck Servers -> Client cached
   
3. Client -> Chunck Server
   
4. Chunck Server return data -> Client


WRITES

- Cases

  - No Primary - on Master

    - Find up to date replicas
    - Pick Primary, Seconday
    - Increments the Version #
    - Tells Primary, Secondaries the Version # --- Lease
    - Master writes Version # to disk


|

.. image:: https://i.imgur.com/TEAFzlL.png


|

Paper Notes
=============

- snapshot
- record

|

.. image:: https://i.imgur.com/a267Lof.jpg


`Reference <https://pdos.csail.mit.edu/6.824/papers/gfs.pdf>`_


|


Operation Log
---------------

- ``operation log``

  - The operation log contains a historical record of critical metadata changes.

  - Serves as a logical time line that defines the order of concurrent operations.

|
- Reliable Store

  - GFS replicate it on multiple remote machines and respond to a client operation only after flushing the corresponding log record to disk both locally and remotely.
  
|
- Recovery

  - replaying the ``operation log``
  - ``checkpoint``
  
    - 當 log 超過某個量級的時候，就會被 system 做成一個 checkpoint
    - 這樣一來 recovery 的時候，系統就只需要將最近一次的 checkpoint 載回來就好
    - checkpoint 以類似 ``B-tree`` 的結構儲存，以加速 recovery、 improves availability
    
      - directly mapped into memory
      - used for namespace lookup without extra parsing

|

- Failure

  - A failure during checkpointing does not affect correctness because the recovery code detects and skips incomplete checkpoints.



|



Terms
------


- relaxed consistency model

|


Related
---------

- `知乎 <https://zhuanlan.zhihu.com/p/28155582>`_











