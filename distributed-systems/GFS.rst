GFS
=====

MIT - 6.824 Distributed Systems, Spring 2020

- `[Schedule] <https://pdos.csail.mit.edu/6.824/schedule.html>`_
- `[Video] <https://www.youtube.com/watch?v=EpIgvowZr00&feature=emb_logo>`_
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
-----

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

Operation

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





