Database Storage II
===================

- `[Schedule] <https://15445.courses.cs.cmu.edu/fall2018/schedule.html>`_
|

- `[Video] <https://www.youtube.com/watch?v=NXRgIsH83xE&list=PLSE8ODhjZXja3hgmuwhf89qboV1kOxMx7&index=4>`_
- `[Slide] <https://15445.courses.cs.cmu.edu/fall2018/slides/04-storage2.pdf>`_
- `[Notes] <https://15445.courses.cs.cmu.edu/fall2018/notes/04-storage2.pdf>`_

|

Disk-Oriented DBMS
--------------------

.. raw:: html

    <img src="https://i.imgur.com/7zZzJLQ.png">


|

Data Representation
-------------------



- Variable Precision Numbers
  
  - ``FLOAT``, ``REAL``

- Fixed Point Precision Numbers

  - ``NUMERIC``, ``DECIMAL``


|

Workloads
----------------

根據不同的 query 需求, 可以分為 OLTP 與 OLAP 兩類

- ``OLTP``

  - On-line Transaction Processing
  
    - Simple queries that read/update a small amount of data that is related to a single entity in the database.
    - 較簡單的一般 query
    - e.g. wiki 新增帳號, 新增文章; 新增商品到購物車, simple operation
    
  - Row store

|

- ``OLAP``

  - On-line Analyitical Processing
  
    - Complex queries that read large portions of the database spanning multiple entities.
    - 需要掃很大部分 DB 內容並計算的 query
    - e.g. Amazon 計算 top 5 暢銷商品
    
  - Column store

|


Storage Models
---------------

- ``N-Ary Storage Model (NSM)``

  - ``row store``
  - 優: faster inserts, updates, deletes; 特定方式查詢很迅速
  - 缺: 假設我要列出所有使用者的名稱的話，就需要幾乎把 user table 裡的所有 record 掃一遍

|

- ``Decomposition Storage Model (DSM)``
  
  - ``column store``
  - 將一個 column 存在同一個 page
    
    - 這樣的話假設要列出某個 column 裡面的所有值就非常迅速
    - e.g. 列出 user table 裡面的所有使用者的名稱
  |
  
  - how to combine tuple
  
    - Choice #1: Fixed-length Offsets
    - Choice #2: Embedded Tuple Ids
  
  |
  - 優: 對於 OLAP query 來說非常迅速好用; Better query processing and data compression.

  - 缺: Slow for point queries, inserts, updates, and deletes because of tuple splitting/stitching.
  
    

|

.. raw:: html

    <img src="https://www.xinjianl.com/wp-content/uploads/2019/01/row_model-700x411.png" width="600px">



.. raw:: html

    <img src="https://www.xinjianl.com/wp-content/uploads/2019/01/column_model-700x362.png" width="600px">
