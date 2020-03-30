Web Scaling
==============

CMU Parallel Computer Architecture and Programming

- `[schedule] <http://www.cs.cmu.edu/afs/cs.cmu.edu/academic/class/15418-f19/www/schedule.html>`_
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

|

Parallelism Scale Out
-----------------------

由於很多 work 是重複的，在者種情況下利用 locality 的特性去做優化就很棒


- 利用 Cache!

  - Cache commonly accessed objects 將常用的物件 cache 起來

    - ex. ``memcached``, in memory key-value store (e.g., a big hash table) 
    - Reduces database load (fewer queries)
    - Reduces web server load

  - CDNs (content distribution networks)


|

名詞
---------

- Session Affinity (Sticky Session)

- Consistency v.s. Coherence

- Over-provisioning

  - Amazon EC2 的 over-provisioning 問題
|

- Scale out v.s. Scale up 

  |
  - Scale Up又稱為垂直擴展（scale vertically），意為在單節點上添加資源，如CPU，內存和存儲，在縱向上擴展從而獲得更多計算或存儲能力；Scale Up初期能夠快速達到升級目的，操作起來相對比較簡單，但隨著計算或存儲的要求越來越高，硬體資源的添加可能已經達到極限，不僅單節點的造價非常昂貴，維護成本很高，而且更容易留下單點故障的隱患。傳統的RAID（Redundant Array of Inexpensive Disks）存儲就是此種模式。

  - Scale Out又稱為水平擴展（scale horizontally），意為在分布式環境下，通過添加節點計算或存儲資源，在橫向上滿足更多的計算存儲需求；隨著計算和存儲單位價格的降低和效率的提升，使用低端的商用（commodity）系統，利用分布式技術可以搭建起「超級計算」中心，以及後來衍生出來的私有或公有雲平台解決方案。 `[ref] <https://kknews.cc/zh-tw/tech/8q52k6e.html>`_


|

- Memcached

  - 是一套分散式的高速緩衝記憶體系統，由LiveJournal的Brad Fitzpatrick開發，但目前被許多網站使用。這是一套開放原始碼軟體，以BSD license授權釋出。
  - `[MemCache 基礎介紹與工作原理] <https://segmentfault.com/a/1190000012950110>`_


