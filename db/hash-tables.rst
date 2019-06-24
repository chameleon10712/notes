Hash Tables
===========


11.6 Static Hashing
===================


- bucket

  - a unit of storage that can store one or more records


- h: K -> B

  - ``h``: hash function
  - ``K``: search-key
  - ``B``: bucket

 

11.6.1 Hash Functions
---------------------

- uniform
- random




11.6.2 Handling of Bucket Overflows
-----------------------------------

發生 overflow 的原因

- Insufficient buckets
- Skew

  - bucket 數量夠多，但是 records 集中在某些 bucket 導致 overflow

|

Solution

- ``overflow buckets``

  - 將裝不下的 records 用 overflow buckets 裝

  - overflow chaining

    - 如果一個 overflow bucket 也裝不下，就用另一個 overflow bucket，並且將所有的 overflow buckets 以 linked-list 的方式串起來。

  - 上述的方法稱為 ``closed hashing``


|

- ``linear probing``

  - 如果 overflow ，則將 records 放置在下一個有空間的 bucket 中
  - 這種方式稱為 ``open hashing``




