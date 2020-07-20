Web Backend Solution
=======================


OS
----

- Process v.s. Thread v.s. Coroutine

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

- Inter-Process Communication

  - Linux: pipes, message queues

|

- Deadlock
  
  - 條件
  
    - **Mutual Exclusion**: One or more than one resource are non-sharable (Only one process can use at a time)
    - **Hold and Wait**: A process is holding at least one resource and waiting for resources.
    - **No Preemption**: A resource cannot be taken from a process unless the process releases the resource.
    - **Circular Wait**: A set of processes are waiting for each other in circular form.





















