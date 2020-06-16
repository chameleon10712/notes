Sorting & Aggregation Algorithms 
===================================

- `[Schedule] <https://15445.courses.cs.cmu.edu/fall2018/schedule.html>`_
|

- `[Video] <https://www.youtube.com/watch?v=9wv-ZzClKks&list=PLSE8ODhjZXja3hgmuwhf89qboV1kOxMx7&index=11>`_
- `[Slide] <https://15445.courses.cs.cmu.edu/fall2018/slides/11-sorting.pdf>`_
- `[Notes] <https://15445.courses.cs.cmu.edu/fall2018/notes/11-sorting.pdf>`_
- Readings: Chapter 12.4-12.5

|

Overview
----------

- 2 way merge sort
- Files are broken up to ``N`` pages
- The DBMS has a finite number of ``B`` fixed-size buffers.

|

2 Way Merge Sort
-------------------

- Each sorted set of pages is called a ``run``.


.. image:: https://i.imgur.com/GB66A4K.png


- Number of passes = 1 + ⌈ log2 N ⌉
- Total I/O cost = 2N ∙ (# of passes)

|

Hashing Aggregate
--------------------

- alternatives to sorting

  - when you only need to remove duplicates, no need for ordering




|

Terms
--------

- bulk loading

  - loading a large volume of data into DB
  - `What does “bulk load” mean? <https://stackoverflow.com/a/4462149>`_



