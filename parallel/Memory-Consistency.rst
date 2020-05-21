Memory Consistency
=====================

CMU - Parallel Computer Architecture and Programming, Fall 2018

- `[Schedule] <http://www.cs.cmu.edu/afs/cs.cmu.edu/academic/class/15418-f18/www/schedule.html>`_
- `[Video] <https://mediaservices.cmu.edu/media/Lecture+18+-+2-26-18/1_ja3vk16j/84714321>`_
- `[Slide] <http://www.cs.cmu.edu/afs/cs.cmu.edu/academic/class/15418-f18/www/lectures/14_consistency.pdf>`_


|


Sequential Consistency (SC)
------------------------------

Def

- accesses of each processor in ``program order``
- all accesses appear in ``sequential order``



Example

- 
  Process 0

  .. code::

    A = 1          (a)
    Ready = 1      (b)


  Process 1

  .. code::

    x = Ready     (c)
    y = A         (d)


  - All locations are initialized to 0

  - Possible outcome for (x,y):

    - (0,0), (0,1), (1,1)
    |

    - 不會出現 (1,0) 的理由: 因為 (1,0) 不符合 Process 0 的 program order , 以 Process 0 的角度來看, Ready = 1 的時候(b), (a) 必然已經執行, 所以不可能



|

Relaxed Consistency Model
-----------------------------



|

Related
--------

- `知乎 - 內存一致性模型Memory Consistency Model <https://zhuanlan.zhihu.com/p/65984694>`_
- `Youtube - Memory Consistency Model <https://www.youtube.com/watch?v=EWTNNm_s8MM>`_
- `Youtube - Relaxed Consistency <https://www.youtube.com/watch?v=1EmifogvkYg>`_





