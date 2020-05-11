Cache Memories
=================

CMU - Intro to Computer Systems, Fall 2016

- `[schedule] <http://www.cs.cmu.edu/afs/cs/academic/class/15213-f16/www/schedule.html>`_

- `[video] <https://scs.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=3395b86e-0bd4-425d-8872-251e714acdd7>`_
- `[slide] <http://www.cs.cmu.edu/afs/cs/academic/class/15213-f16/www/lectures/12-cache-memories.pdf>`_

|

.. image:: https://i.imgur.com/srLI15Q.png

|
|

Direct-Mapped Cache
---------------------

- `Example <https://www.youtube.com/watch?v=RqKeEIbcnS8>`_

E-way Set Associate Cache, E=1 時就是 Dirct-Mapped Cache

.. image:: https://i.imgur.com/0vuNfre.png


|
|

E-way Set Associate Cache
---------------------------

.. image:: https://i.imgur.com/IuW2mEY.png

利用硬體同時比較哪一個 tag match

|
|

Writes 
--------

- write hit

  - write through

    - write immediately to memory

  - write back

    - defer write to memory until replacement of line 當要替換時才寫回 memory
  
    - need a dirty bit

- write miss

  - write allocate
  
    - load into cache, update line in cache
    
  - no-write allocate
  
    - write straight to memory, does not load into cache 直接寫入記憶體, 不寫入 cache
