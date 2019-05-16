Thread
======

4.1.2 Benefits

- **Responsiveness**

  - Multithreading an interactive application may allow a program to continue running even if part of it is blocked or is performing a lengthy operation, thereby increasing responsiveness to the user

- **Resource sharing**

- **Economy**

- **Scalability**

  - The benefits of multithreading can be even greater in a multiprocessor architecture, where threads may be running in parallel on different processing cores.



4.2.2 Types of Parallelism

- Data parallelism

  focuses on distributing subsets of the same data
  across multiple computing cores and performing the same operation on each
  core.


- Task parallelism

  involves distributing not data but tasks (threads) across
  multiple computing cores. Each thread is performing a unique operation.
  Different threads may be operating on the same data, or they may be operating
  on different data.


4.5.1 Thread Pools

