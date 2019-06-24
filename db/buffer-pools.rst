Buffer Pools
============






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

- Buffer replacement strategy

  - least recently used (LRU)
  - toss-immediate strategy
  
    - 假設已經處理完某個 query，則那個 block 就可以丟掉了。用過即丟。

|

- Pinned blocks

  - 當某個 block 正在 update 時，不能讓其他人寫入這個 block。這種 block 稱為 pinned block。
  - 很少 OS 支援 pinned blocks

|

- Forced output of blocks

  - There are situations in which it is necessary to write back the block to disk, even though the buffer space that it occupies is not needed
