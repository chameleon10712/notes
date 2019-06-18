Database Storage II
===================

- `[Schedule] <https://15445.courses.cs.cmu.edu/fall2018/schedule.html>`_
|

- `[Video] <https://www.youtube.com/watch?v=NXRgIsH83xE&list=PLSE8ODhjZXja3hgmuwhf89qboV1kOxMx7&index=4>`_
- `[Slide] <https://15445.courses.cs.cmu.edu/fall2018/slides/04-storage2.pdf>`_
- `[Notes] <https://15445.courses.cs.cmu.edu/fall2018/notes/04-storage2.pdf>`_

|

Data Representation
-------------------



- Variable Precision Numbers
  
  - ``FLOAT``, ``REAL``

- Fixed Point Precision Numbers

  - ``NUMERIC``, ``DECIMAL``


Workloads
---------

- OLTP

  - On-line Transaction Processing
  
    - Simple queries that read/update a small amount of data that is related to a single entity in the database.
  - Row store

|

- OLAP

  - On-line Analyitical Processing
  
    - Complex queries that read large portions of the database spanning multiple entities.
  - Column store



Storage Models
--------------

- N-Ary Storage Model (NSM)
- Decomposition Storage Model (DSM)


.. raw:: html

    <img src="https://www.xinjianl.com/wp-content/uploads/2019/01/row_model-700x411.png" width="600px">



.. raw:: html

    <img src="https://www.xinjianl.com/wp-content/uploads/2019/01/column_model-700x362.png" width="600px">
