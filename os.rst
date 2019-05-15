- concurrency
- parallelism


Thread
======

4.1.2 Benefits
--------------

- **Responsiveness**

  - Multithreading an interactive application may allow a program to continue running even if part of it is blocked or is performing a lengthy operation, thereby increasing responsiveness to the user

- **Resource sharing**

- **Economy**

- **Scalability**

  - The benefits of multithreading can be even greater in a multiprocessor architecture, where threads may be running in parallel on different processing cores.



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

4.5.1 Thread Pools
------------------


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

- Mutual exclusion

  - at least one resource must be nonsharable

- Hold and wait
- No preemption
- Circular wait


7.3 Methods for Handling Deadlocks
----------------------------------

Deadlock prevention
+++++++++++++++++++

provides a set of methods to ensure that at least one of the necessary conditions

- Mutual Exclusion

  - we cannot prevent deadlocks by denying the mutual-exclusion condition, because some resources are intrinsically nonsharable.
  
    - ex. a mutex lock cannot be simultaneously shared by several processes

- Hold and Wait

  - One protocol that we can use requires each process to request and be allocated all its resources before it begins execution.
  - An alternative protocol allows a process to request resources only when it has none.
  
    -  A process may request some resources and use them. Before it can request any additional resources, it must release all the resources that it is currently allocated.

  - disadvantages of these protocols
  
    - resource utilization may be low, since resources may be allocated but unused for a long period
    - starvation is possible
    
      - A process that needs several popular resources may have to wait indefinitely, because at least one of the resources that it needs is always allocated to some other process

- No Preemption

  - protocol 1
  
    - If a process is holding some resources and requests another resource that cannot be immediately allocated to it (that is, the process must wait), then all resources the process is currently holding are preempted (implicitly released). The process will be restarted only when it can regain its old resources, as well as the new ones that it is requesting.

  - prootcol 2 
  
    - a process requests some resources 
    
      => if resources are not available
   
      => check whether they are allocated to some other process that is waiting for additional resources
      
      => preempt the desired resources from the waiting process and allocate them to the requesting process
      
      => or waiting, some of its resources may be preempted, but only if another process requests them
  
    - This protocol is often applied to resources whose state can be easily saved and restored later, such as CPU registers and memory space. It cannot generally be applied to such resources as mutex locks and semaphores.


Deadlock avoidance
++++++++++++++++++

requires that the operating system be given additional
information in advance concerning which resources a process will request
and use during its lifetime











