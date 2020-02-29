Hash Tables
===========

- `[Schedule] <https://15445.courses.cs.cmu.edu/fall2018/schedule.html>`_
|

- `[Video] <https://www.youtube.com/watch?v=ByG1IMM6Ua8&list=PLSE8ODhjZXja3hgmuwhf89qboV1kOxMx7&index=6>`_
- `[Slide] <https://15445.courses.cs.cmu.edu/fall2018/slides/06-hashtables.pdf>`_
- `[Notes] <https://15445.courses.cs.cmu.edu/fall2018/notes/06-hashtables.pdf>`_
- Readings: Chapter 11.6-11.7

|


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

  - ``overflow chaining``

    - 如果一個 overflow bucket 也裝不下，就用另一個 overflow bucket，並且將所有的 overflow buckets 以 linked-list 的方式串起來，這種方式稱為 ``overflow chaining``。

  - 上述的方法稱為 ``closed hashing``


|

- ``linear probing``

  - 如果 overflow ，則將 records 放置在下一個有空間的 bucket 中，這種方式稱為 ``open hashing`` 。
  - ``open hashing``
  
    - the set of buckets is fixed, and there are no overflow chains

|

Open Hashing & Closed Hashing

- ``open hashing`` 常被 compilers 、 assemblers 用來建 symbol tables。 而 ``closed hashing`` 在 DB 比較常見。
- 因為 open hashing 的做法會難以處理 delete 的狀況，而 compilers 只需要處理 lookup 跟 insert 兩種操作。

|

11.7 Dynamic Hashing
=====================

多數的 Database 資料會隨著時間越來越多，如果使用 static hashing 的話，會有三種選擇

1. 根據現有的 Database 資料量選擇 hash function，這個做法會導致之後當 DB 資料量增加時，效能因為 overflow 減小。
2. 根據未來的 Database 資料量選擇 hash function，這個做法可能導致前期空間浪費。
3. 在適當的時機重新組織(reorganize) hash structure，這個做法費時費力。

而 Dynamic Hashing 可以讓 hash function 根據現有的資料量成長或縮減動態的改變 hash function


接下來我們要介紹的是其中一種名為 ``extendable hashing`` 的 dynamic hashing

|

11.7.1 Data Structure
----------------------

``Extendable Hashing`` 藉由分割與合併 buckets 來動態配合資料量大小

假設我們選擇一個 hash function ``h``，這個 hash function 產生非常大範圍的 b-bit binary integer (typically b=32)。由於 2^32 這個數字實在太大了，在 extendable hashing 裡面，我們只根據需求來 create buckets ，當有新的 record 的時候才去 create。

|

11.7.2 Queries and Updates
----------------------------

|

11.7.3 Static Hashing versus Dynamic Hashing
-------------------------------------------------

Extendable Hashing 

- 效能不會隨著 DB 的資料量增加而減少，並且不會浪費空間
- 缺點是 lookup 的時候不能直接找到 bucket 而須先查看 bucket address table (additional level of indirection)




