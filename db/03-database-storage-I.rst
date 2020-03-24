Database Storage I
===================



- `[Schedule] <https://15445.courses.cs.cmu.edu/fall2018/schedule.html>`_
|


- `[Video] <https://www.youtube.com/watch?v=uuX4PQXBeos&list=PLSE8ODhjZXja3hgmuwhf89qboV1kOxMx7&index=3>`_
- `[Slide] <https://15445.courses.cs.cmu.edu/fall2018/slides/03-storage1.pdf>`_
- `[Notes] <https://15445.courses.cs.cmu.edu/fall2018/notes/03-storage1.pdf>`_
- Readings: Chapter 10.1-10.2, 10.5-10.6

|

Course Outline
--------------------

- Relational Databases

- Database Storage

  |
  - How to read / write data
  - What that data looks like on disk. 實際在硬碟中 DB 如何儲存資料
  - Storage Scheme / Disk Manager

|

- Execution

- Concurrency Controy

- Recovery

- Distributed Databases

- Potpourri

|

Storage Hierarchy
-------------------

faster, slower ----------------------------------------> slower, larger

CPU Register, CPU cache, DRAM | SSD, HDD, Network Storage

---------- Volatile ---------------|--------Non-Volatile---------

|
- Volatile

  - Random Access
  - Byte-Addressable
|
- Non-Volatile

  - Sequtial Access
  - Block-Addressable

|

- Memory

  - DRAM
  
- Disk

  - SSD, HDD, Network Storage

|

Raw Storage
-----------


- File Storage
- Page Layout
- Tuple Layout


|


CH 10.5 File Organization
=========================

- Each file is also logically partitioned into fixed-length storage units called blocks
- A block may contain several records

  - no record is larger than a block
  - each record is entirely contained in a single block


- records

  - fixed-length records
  
    - easier to implement 
    
  - variable-length records



10.5.1 Fixed-Length Records
---------------------------

- file header
- free list
  
  - 紀錄 deleted records，下一個 insertion 會從 free list 開始找 free space ; free list 沒有空間才 append 到檔案尾端



10.5.2 Variable-Length Records
------------------------------

Questions
+++++++++

- How to represent a single record in such away that individual attributes can be extracted easily.
- How to store variable-length records within a block, such that records in a block can be extracted easily.



Q1
++

- [an initial part with fixed length attributes] +  [data for variable-length attributes]

  - fixed length attributes

    - such as ``numeric`` values, ``dates``, or ``fixed-length character strings``

  - Variable-length attributes

    - such as ``varchar``
    - are represented in the initial part of the record by a pair (offset, length)

|


- null bitmap

  - indicates which attributes of the record have a null value



Q2
++

slotted-page structure

- organizing records within a block



CH 10.6 Organization of Records in Files
========================================

- Heap file organization
- Sequential file organization
- Hashing file organization



10.6.1 Sequential File Organization
-----------------------------------

- Sequential File

  - A sequential file is designed for efficient processing of records in sorted order based on some search key.

- Search Key

  - A search key is any attribute or set of attributes



10.6.2 Multitable Clustering File Organization
----------------------------------------------

- multitable clustering file organization

  - a file organization that stores related records of two or more relations in each block.

