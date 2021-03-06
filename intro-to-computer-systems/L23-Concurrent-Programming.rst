Concurrent Programming
=========================


CMU - Intro to Computer Systems, Fall 2017

- `[schedule] <http://www.cs.cmu.edu/afs/cs/academic/class/15213-f16/www/schedule.html>`_

- `[video] <https://www.bilibili.com/video/BV1g4411L7TB?p=28>`_
- `[slide] <http://www.cs.cmu.edu/afs/cs/academic/class/15213-f17/www/lectures/23-concprog.pdf>`_

|

Classical problem classes of concurrent programs
--------------------------------------------------


- Race
- Deadlock
- Livelock / Starvation / Fairness

|

Approaches for Writing Concurrent Servers
--------------------------------------------

- Process-based

  - Kernel 自動切換
  - each flow 有自己的 address space (每個 flow 獨立)

- Event-based

  - Programmer 手動切換
  - 所有 flow 共享 address space
  - I/O multiplexing

- Thread-based

  - Kernel 自動切換
  - each flow shared address space
  - Process-based 與 Event-based 的混合體 (Hybrid) 
  
|

  

Process-based Servers
------------------------

- spawn (fork) separate process for each client
- server process 一定要主動砍掉 zombie children 

  - to avoid fatal memory leak
|
- pros

  - 同時處理多個 connection
  - clean sharing model
  - simple code

- cons

  - additional overhead for process control
  - process 之間的溝通需要 interprocess communication (IPC)

|


Event-based Servers
-----------------------

- pros

  - One process with one address space

    - simpler to debug, only single-step with a debugger
  - No process or thread control overhead

    - 所以是 high performance web server / search engine 的設計首選 e.g. Node.js, nginx, Tornado

- cons

  - complex code
  - hard to provide fine-grained concurrency

    - how to deal with partial HTTP request headers

  - single thread of control, 不會享有 multi-core 的好處

|


Thread-based Servers
----------------------

concurrent thread execution

- single core processor

  - simulate parallelism by time slicing 


- multi-core processor

  - can have true parallelism 可以做到真正的平行


