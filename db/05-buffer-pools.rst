Buffer Pools
============



- `[Schedule] <https://15445.courses.cs.cmu.edu/fall2018/schedule.html>`_
|


- `[Video] <https://www.youtube.com/watch?v=_vRG1ksPlXs&list=PLSE8ODhjZXja3hgmuwhf89qboV1kOxMx7&index=5>`_
- `[Slide] <https://15445.courses.cs.cmu.edu/fall2018/slides/05-bufferpool.pdf>`_
- `[Notes] <https://15445.courses.cs.cmu.edu/fall2018/notes/05-bufferpool.pdf>`_
- Readings: Chapter 10.5-10.8

|

TERMS
=======

- ``buffer`` 

  - main memory 裡面放置 DB disk blocks copies 的地方

- ``buffer manager`` 

  - 用來管理 buffer 的 subsystem

- ``data dictionary`` 

  - DB 的 metadata, 又稱為 ``system catalog``


|



DATABASE STORAGE
===================

``Spatial Control``:

- The goal is to keep pages that are used together often as physically close together as possible on disk.
- 將常互相用到的 pages 位置放置在 Disk 上鄰近區域


``Temporal Control``:

- The goal is minimize the number of stalls from having to read data from disk.
- 減少從硬碟讀取資料的時間。

|

DISK-ORIENTED DBMS

``Buffer Pool``

- DB 在 Memory 的工作區
- an in-memory cache of pages read from disk


|

``Page Table``



- The page table keeps track of pages that are currently in memory.
- Also maintains additional meta-data per page:

  - ``Pin/Reference Counter``
  
    - Number of threads touching that page. 目前正在 read 這個 page 的 thread 數量
    - If I want to read it I pin it. 防止這個 page 被修改或被 swap out。
  
  - ``Dirty Flag``
  
    - 如果要修改某個 page ，就放一個 ``latch`` 在上面 (can be implemented as mutex) ，表示正在修改中。 並且標示 dirty flag 表示這個 page 已被修改。

|

LOCKS VS. LATCHES

``Locks``:

- Protect the database logical contents from other transactions
  
  - transaction 跟 transaction 之間不能互相干擾。不能影響彼此正要讀或寫的 records (lock table) 。

- Need to be able to rollback changes
- Use to protect database entities ex. ``tuples``, ``tables``, ``indexes``

``Latches``:

- Protects the critical sections of the DBMS internal data structure from other threads

  - thread 跟 thread 之間不能互相干擾。不能污染彼此正要讀或寫的 page。
   
- Do not need to be able to rollback changes


In SQL you can get a lock but you cannot get a latch ，因為 latch 是 DB 用來確保 page 不被污染用的。

|

PAGE TABLE VS. PAGE DIRECTORY

``page directory``:

- The page directory is the mapping from page ids to page locations in the database files.
  
  
  - All changes must be recorded on disk to allow the DBMS to find on restart. 
  - 儲存 page id 以及對應的 location。 所有的改動都必須寫回 Disk ，這樣 crash 時資料才不會不見。

 


``page table``:

- The page table is the mapping from page ids to a copy of the page in buffer pool frames.

  - This is an in-memory data structure that does not need to be stored on disk.
  - 用來記錄 Memory 裡面有哪些 copy 。不見就不見了。

|


MULTIPLE BUFFER POOLS

- 為了避免許多 threads 同時讀寫某個 page ，每個 thread 都在拿 latch ，許多 DB 用 ``multiple buffer pools`` 解決這個問題。
- 當某個 thread 要 access 某個 page 時，首先會先用 hash function 尋找該 page 的 buffer pool 

|

- ex. MySQL, DB2 ...

|


PRE-FETCHING

The DBMS can also optimize by pre fetching pages based on the query plan.

- ``Sequential Scans``  

  - 較常見
  - 如果認知到某個 query 會 read 接下來幾個連續的 page ，則預先將這些 page 放到 buffer pool ( ``pre-fetch`` )
|

- ``Index Scans``

  - 假設要 traverse a tree，那麼就可以預測下一個要 fetch 的 page 


|

10.5 File Organization
=========================

- fixed-length records

- variable-length records



|

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

  - ``least recently used (LRU)``
  
    - OS 常用，但是 DB 可以根據使用情境，預測得更準確。
    - 很多 DB 還是用 LRU
  
  - ``toss-immediate``
  
    - 假設已經處理完某個 query，則那個 block 就可以丟掉了。用過即丟。
  
  - ``most recently used (MRU)``

|

- ``Pinned blocks``

  - 當某個 block 正在 update 時，不能讓其他人寫入這個 block。這種 block 稱為 pinned block。
  - 很少 OS 支援 pinned blocks

|

- Forced output of blocks

  - There are situations in which it is necessary to write back the block to disk, even though the buffer space that it occupies is not needed
