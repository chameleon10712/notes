Buffer Pools
============



- `[Schedule] <https://15445.courses.cs.cmu.edu/fall2018/schedule.html>`_
|


- `[Video] <https://www.youtube.com/watch?v=_vRG1ksPlXs&list=PLSE8ODhjZXja3hgmuwhf89qboV1kOxMx7&index=5>`_
- `[Slide] <https://15445.courses.cs.cmu.edu/fall2018/slides/05-bufferpool.pdf>`_
- `[Notes] <https://15445.courses.cs.cmu.edu/fall2018/notes/05-bufferpool.pdf>`_
- Readings: Chapter Chapter 10.5-10.8

|


``page table``



- The page table keeps track of pages that are currently in memory.
- Also maintains additional meta-data per page:

  - ``Pin/Reference Counter``
  
    - Number of threads touching that page. 目前正在 read 這個 page 的 thread 數量
    - If I want to read it I pin it. 防止這個 page 被修改或被 swap 掉。
  
  - ``Dirty Flag``
  
    - 如果要修改某個 page ，就放一個 ``latch`` 在上面 (can be implemented as mutex) ，表示正在修改中。 並且標示 dirty flag 表示這個 page 已被修改。



10.7 Data-Dictionary Storage
=============================

Data Dictionary
+++++++++++++++

- DB 的 meta data
- 又叫做 system catalog

|

- 存基本資訊 (table name, attributes, relations 數量, storage organization 儲存方式 ex. sequential, hash, heap 等等)
- 基本上也用 relational 的方式儲存
- often stored in a nonnormalized form to achieve fast access.



10.8 Database Buffer
====================

- Buffer Replacement Policies

  - least recently used (LRU)
  
    - OS 常用，但是 DB 可以根據使用情境，預測得更準確。
    - 很多 DB 還是用 LRU
  
  - toss-immediate
  
    - 假設已經處理完某個 query，則那個 block 就可以丟掉了。用過即丟。
  
  - most recently used (MRU)

|

- Pinned blocks

  - 當某個 block 正在 update 時，不能讓其他人寫入這個 block。這種 block 稱為 pinned block。
  - 很少 OS 支援 pinned blocks

|

- Forced output of blocks

  - There are situations in which it is necessary to write back the block to disk, even though the buffer space that it occupies is not needed
