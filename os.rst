Thread
======

4.1.2 Benefits
--------------

1. **Responsiveness**: Multithreading an interactive application may allow a program to continue running even if part of it is blocked or is performing a lengthy operation, thereby increasing responsiveness to the user

2. **Resource sharing**

3. **Economy**

4. **Scalability**: The benefits of multithreading can be even greater in a multiprocessor architecture, where threads may be running in parallel on different processing cores.

4.2.2 Types of Parallelism
---------------------------

- Data parallelism

focuses on distributing subsets of the same data
across multiple computing cores and performing the same operation on each
core.


- Task parallelism

involves distributing not data but tasks (threads) across
multiple computing cores. Each thread is performing a unique operation.
Different threads may be operating on the same data, or they may be operating
on different data.


Deadlock
========

7.1 System Model
----------------

mutex locks & semaphore => a common source of deadlock

a process may utilize a resource in a following sequence

1. Request
2. Use
3. Release

A system table records whether each resource is free or allocated. For each
resource that is allocated, the table also records the process to which it is
allocated. If a process requests a resource that is currently allocated to another
process, it can be added to a queue of processes waiting for this resource.


7.2 Necessary Conditions
------------------------

1. Mutual exclusion
2. Hold and wait
3. No preemption
4. Circular wait


7.3 Methods for Handling Deadlocks
----------------------------------

Deadlock prevention
+++++++++++++++++++

provides a set of methods to ensure that at least one of the necessary conditions

Deadlock avoidance
++++++++++++++++++

requires that the operating system be given additional
information in advance concerning which resources a process will request
and use during its lifetime











