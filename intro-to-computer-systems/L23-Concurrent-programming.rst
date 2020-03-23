Concurrent Programming
=========================


CMU - Intro to Computer Systems, Fall 2016

- `[schedule] <http://www.cs.cmu.edu/afs/cs/academic/class/15213-f16/www/schedule.html>`_

- `[video] <https://scs.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=0be3c53f-5d35-40f0-a5ab-55897a2c91a5>`_
- `[slide] <http://www.cs.cmu.edu/afs/cs/academic/class/15213-f16/www/lectures/23-concprog.pdf>`_

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
  - Detail
  
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
  


- Event-based

  - Programmer 手動切換
  - 所有 flow 共享 address space
  - I/O multiplexing
  - Detail
  
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


- Thread-based

  - Kernel 自動切換
  - each flow shared address space
  - Process-based 與 Event-based 的混合體 (Hybrid) 
  
|

  










