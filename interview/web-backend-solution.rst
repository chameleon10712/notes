Web Backend Solution
=======================


OS
----

Process v.s. Thread v.s. Coroutine
+++++++++++++++++++++++++++++++++++++

- **Short answer**:

  With threads, the operating system switches running threads preemptively according to its scheduler, 
  which is an algorithm in the operating system kernel. 
  With coroutines, the programmer and programming language determine when to switch coroutines; 
  in other words, tasks are cooperatively multitasked by pausing and resuming functions at set points, 
  typically (but not necessarily) within a single thread.

  - Reference

    - `Difference between a “coroutine” and a “thread”? <https://stackoverflow.com/questions/1934715/difference-between-a-coroutine-and-a-thread>`_


- Coroutine

  - Reference
  
    - `Coroutine in Python <https://www.geeksforgeeks.org/coroutine-in-python/>`_


|

Inter-Process Communication
++++++++++++++++++++++++++++++

- Linux: pipes, message queues

|

Deadlock 死鎖
+++++++++++++++
  
- 原因:

  - 競爭資源
  - 程序推進順序不當

- 必要條件:

  1.互斥條件 Mutual Exclusion: 

  - One or more than one resource are non-sharable (Only one process can use at a time)

  2.請求和保持條件 Hold and Wait: 

  - A process is holding at least one resource and waiting for resources.

  3.不剝奪條件 No Preemption: 

  - A resource cannot be taken from a process unless the process releases the resource.

  4.環路等待條件 Circular Wait: 

  - A set of processes are waiting for each other in circular form.

|
- 處理死鎖基本方法:

  - 預防死鎖(摒棄除1以外的條件)
  - 避免死鎖(銀行家算法)
  - 檢測死鎖(資源分配圖)
  - 解除死鎖
  - 剝奪資源
  - 撤銷進程

|
- Reference

  - `Introduction of Deadlock in Operating System <https://www.geeksforgeeks.org/introduction-of-deadlock-in-operating-system/>`_
  - `Python Interview <https://github.com/taizilongxu/interview_python#3-%E6%AD%BB%E9%94%81>`_

|

Scheduling Algorithms 調度算法
+++++++++++++++++++++++++++++++++

- 先來先服務(FCFS, First Come First Serve)
- 短作業優先(SJF, Shortest Job First)
- 最高優先權調度(Priority Scheduling)
- 時間片輪轉(RR, Round Robin)
- 多級反饋隊列調度(multilevel feedback queue scheduling)


實時調度算法:

- 最早截至時間優先EDF
- 最低鬆弛度優先LLF






