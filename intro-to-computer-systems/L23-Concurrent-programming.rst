Concurrent Programming
=========================


CMU - Intro to Computer Systems, Fall 2016

- `[schedule] <http://www.cs.cmu.edu/afs/cs/academic/class/15213-f16/www/schedule.html>`_

- `[video] <https://scs.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=0be3c53f-5d35-40f0-a5ab-55897a2c91a5>`_
- `[slide] <http://www.cs.cmu.edu/afs/cs/academic/class/15213-f16/www/lectures/23-concprog.pdf>`_

|

Concurrent Programming is Hard
---------------------------------

concurrent programming 可能造成的經典問題

- race
- deadlock
- livelock / starvation / fairness

|

Approaches for Writing Concurrent Servers
--------------------------------------------

- Process-based

  - Kernel 自動切換
  - each flow 有自己的 address space (每個 flow 獨立)
  - spawn (fork) separate process for each client
  
|

- Event-based

  - Programmer 手動切換
  - 所有 flow 共享 address space
  - I/O multiplexing
|

- Thread-based

  - Kernel 自動切換
  - each flow shared address space
  - Process-based 與 Event-based 的混合體 (Hybrid) 
  
|

  










