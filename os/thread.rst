Thread
======

4.1.2 Benefits

- Responsiveness

  - Multithreading an interactive application may allow a program to continue running even if part of it is blocked or is performing a lengthy operation, thereby increasing responsiveness to the user

- Resource sharing

- Economy

- Scalability

  - The benefits of multithreading can be even greater in a multiprocessor architecture, where threads may be running in parallel on different processing cores.



4.2.2 Types of Parallelism

- Data parallelism

  - focuses on distributing subsets of the same data across multiple computing cores and performing the same operation on each core.


- Task parallelism

  - involves distributing not data but tasks (threads) across multiple computing cores. Each thread is performing a unique operation. Different threads may be operating on the same data, or they may be operating on different data.


4.5 Implicit Threading
----------------------

Thread Pools
++++++++++++

benefits

- Servicing a request with an existing thread is faster than waiting to create a thread

- A thread pool limits the number of threads that exist at any one point. This is particularly important on systems that cannot support a large number of concurrent threads.

- Separating the task to be performed from the mechanics of creating the task allows us to use different strategies for running the task. For example, the task could be scheduled to execute after a time delay or to execute periodically


4.6 Threading Issues
--------------------

issues

- The fork() and exec() System Calls
- Signal Handling
- Thread Cancellation
















