Web Scaling
==============

CMU Parallel Computer Architecture and Programming

- `[schedue] <http://www.cs.cmu.edu/afs/cs.cmu.edu/academic/class/15418-f19/www/schedule.html>`_
- `[slide] <http://www.cs.cmu.edu/afs/cs.cmu.edu/academic/class/15418-f19/www/lectures/16_webscaling.pdf>`_


因為投影片內容含有大量圖示，所以這篇筆記偏向補充名詞解釋

|


Performance Issues
--------------------

- Parallelism
- Locality 
  
  - Locality of reference 存取局部性
  - 存取局部性分為兩種基本形式，一種是時間局部性 (temporal locality)，另一種是空間局部性(spatial locality)
  - 時間局部性指的是，程式在執行時，最近剛剛被參照過的一個記憶體位置容易再次被參照

    - ex. local variable in function

  - 空間局部性指的是，最近參照過的記憶體位置以及其周邊的記憶體位置容易再次被使用

    - ex. loop

|

A Simple Parallel Web Server
------------------------------

What ``factors`` would you consider in setting
the value of ``N`` for a multi-core web server?


- Parallelism

- Latency hiding

  - hide long-latency disk read operations (by context switching between worker processes) 

- Concurrency

- Footprint

  - don’t want too many threads so that aggregate working set of all threads causes ``thrashing``
    
    |
    - ``thrashing`` occurs when a computer's virtual memory resources are overused, leading to a constant state of paging and page faults, inhibiting most application-level processing.




名詞
---------

- Session Affinity (Sticky Session)

- Consistency v.s. Coherence

- Over-provisioning





