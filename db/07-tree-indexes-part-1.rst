Tree Indexes Part I
======================


- `[Schedule] <https://15445.courses.cs.cmu.edu/fall2018/schedule.html>`_
|

- `[Video] <https://www.youtube.com/watch?v=VHSDhMO63ww&list=PLSE8ODhjZXja3hgmuwhf89qboV1kOxMx7&index=7>`_
- `[Slide] <https://15445.courses.cs.cmu.edu/fall2018/slides/07-trees1.pdf>`_
- `[Notes] <https://15445.courses.cs.cmu.edu/fall2018/notes/07-trees1.pdf>`_
- Readings: Chapter 11.1-11.4

|


Indexing and Hashing
=======================

由於查詢的資料通常都只占 database 資料裡面的一小部分，每一個 record 慢慢比對實在太沒效率，所以一般 DB 都會設計特別的結構去滿足快速查詢的需求。

Basic Concepts
----------------

兩種基本的 indices:

- ``Ordered indices`` : 指標即代表順序

- ``Hash indices`` : 代表一個 hash 值


上述兩種 indices 並沒有誰比較好，兩種 indices 都有個別適合的使用情境

--


搜尋:

- ``search key`` 

  - An attribute or set of attributes used to look up records in a file is called a ``search key``
  - 與 ``primary key``, ``candidate key``, ``superkey`` 意義上不ㄧ樣




Ordered Indices
-----------------


- ``clustering index`` (``primary index``)

  - an index whose search key also defines the sequential order of the file
  - an index that allows the records of a file to be read in an order that corresponds to the physical order in the file
  - The search key of a clustering index is often the primary key
|

- ``nonclustering index``

  - Indices whose search key specifies an order different from the sequential order of the file are called ``nonclustering index``
  - ``secondary index``

--

- ``index-sequential files``

|

Dense and Sparse Indices
++++++++++++++++++++++++++

- ``index entry``
- ``index record``


--

- ``Dense index``

- ``Sparse index``

|

B+-Tree Index Files
--------------------------



|

B+-Tree Extensions
--------------------------





