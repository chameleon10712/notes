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












