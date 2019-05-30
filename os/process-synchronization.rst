Ch5. Process Synchronization
=============================



- cooperating process

  - A cooperating process is one that can affect or be affected by other processes executing in the system.
  - Cooperating processes can either
  
    - directly share a logical address space (that is, both code and data) or 
    - be allowed to share data only through files or messages.


- race condition

  - def: 
  
    - several processes access and manipulate the same data concurrently and the outcome of the execution depends on the particular order in which the access takes place, is called a race condition.
  
  - To guard against the race condition above, we need to ensure that only one process at a time can be manipulating the variable counter. To make such a guarantee, we require that the processes be synchronized in some way.



The Critical-Section Problem
----------------------------

- critical section

  - when one process is executing in its critical section, no other process is allowed to execute in its critical section.
  - The **critical-section problem** is to design a protocol that the processes can use to cooperate. 
    
    - entry section
    - exit section
    - remainder section



Solution to Critical-Section Problem
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

A solution to the critical-section problem must satisfy the following three requirements:

- Mutual exclusion
- Progress
- Bounded waiting


Two general approaches are used to handle critical sections in operating systems:

- preemptive kernels
- nonpreemptive kernels


Peterson's Solution
+++++++++++++++++++

software-based solution to the critical-section problem


Synchronization Hardware
++++++++++++++++++++++++

some simple hardware instructions that are available on many systems and showing how they can be used effectively in solving the critical-section problem


Mutex Locks
+++++++++++


The hardware-based solutions to the critical-section problem presented in Section 5.4 are complicated as well as generally inaccessible to application programmers. Instead, operating-systems designers build software tools to solve the critical-section problem. The simplest of these tools is the **mutex lock**.

- busy waiting

  - While a process is in its critical section, any other process that tries to enter its critical section must loop continuously in the call to ``acquire()``.

- spinlock

  - this type of mutex lock is also called a spinlock because the process “spins” while waiting for the lock to become available.



Semaphores
++++++++++

A more robust tool that can behave similarly to a mutex lock but can also provide more sophisticated ways for processes to synchronize their activities.

- counting semaphore
- binary semaphore


Deadlocks and Starvation
************************

The implementation of a semaphore with a waiting queue may result in a situation where two or more processes are waiting indefinitely for an event that can be caused only by one of the waiting processes. The event in question is the execution of a signal() operation. When such a state is reached, these processes are said to be deadlocked.





