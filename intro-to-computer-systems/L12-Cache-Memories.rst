Cache Memories
=================

CMU - Intro to Computer Systems, Fall 2016

- `[schedule] <http://www.cs.cmu.edu/afs/cs/academic/class/15213-f16/www/schedule.html>`_

- `[video] <https://scs.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=3395b86e-0bd4-425d-8872-251e714acdd7>`_
- `[slide] <http://www.cs.cmu.edu/afs/cs/academic/class/15213-f16/www/lectures/12-cache-memories.pdf>`_

|

.. image:: https://i.imgur.com/srLI15Q.png

1. 首先用 set index 拿到你要的 set
2. 將該 set 裡的所有 lines 的 tag 跟你的 tag 做比較，找出你要的 line 位置
3. 使用 block offset 算出你的 data 位於 line 的哪裡(where the data begins)
4. if tag doesn't match -> miss



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

- write-hit

  - ``write-through``

    - write immediately to memory

  - ``write-back``

    - defer write to memory until replacement of line 當要替換時才寫回 memory
  
    - need a ``dirty bit``

- write-miss

  - ``write-allocate``
  
    - load into cache, update line in cache
    
  - ``no-write-allocate``
  
    - write straight to memory, does not load into cache 直接寫入記憶體, 不寫入 cache

- typical

  - ``write-back`` + ``write-allocate``

|

Memory Mountain
-------------------

|
|

Term
---------------


Cache Line
++++++++++++

- cache line 是 cpu cache 中的最小快取單位
- 主流的 CPU Cache 的 Cache Line 大小多為 64 Bytes


|
|




Related
----------

- `Cache的基本原理 <https://zhuanlan.zhihu.com/p/102293437>`_
- `L1，L2，L3 Cache究竟在哪裡？ <https://zhuanlan.zhihu.com/p/31422201>`_
- `Cache為什麼有那麼多級？為什麼一級比一級大？是不是Cache越大越好？ <https://zhuanlan.zhihu.com/p/32058808>`_
- `試圖）深入理解Cache <https://jcf94.com/2018/09/04/2018-09-04-cache/>`_

- `Cache Effect <http://igoro.com/archive/gallery-of-processor-cache-effects/>`_

|

jserv

- `HackMD - 現代處理器設計: Cache 原理和實際影響 <https://hackmd.io/@sysprog/HkW3Dr1Rb?type=view#%E7%8F%BE%E4%BB%A3%E8%99%95%E7%90%86%E5%99%A8%E8%A8%AD%E8%A8%88-Cache-%E5%8E%9F%E7%90%86%E5%92%8C%E5%AF%A6%E9%9A%9B%E5%BD%B1%E9%9F%BF>`_

- `YouTube <https://www.youtube.com/watch?v=ceER2kqQ9tA>`_

|
