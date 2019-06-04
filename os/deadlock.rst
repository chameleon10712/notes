

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

- prevent deadlocks by limiting how requests can be made
- side effects

  - low device utilization
  - reduced system throughput




Methods
^^^^^^^
provides a set of methods to ensure that at least one of the necessary conditions

- Mutual Exclusion

  - we cannot prevent deadlocks by denying the mutual-exclusion condition, because some resources are intrinsically nonsharable.
  
    - ex. a mutex lock cannot be simultaneously shared by several processes

- Hold and Wait

  - protocol 1: that we can use requires each process to request and be allocated all its resources before it begins execution.
  - protocol 2: allows a process to request resources only when it has none.
  
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



- Circular Wait

  - 給每個 resource type 一個編號，request 順序須依照編號小到大; 如果要 request 一個編號比當前持有的更小的 resource ，則必須先釋放當前持有的 resource
  
    - the process can request instances of resource type Rj if and only if F(Rj) > F(Ri)
    - require that a process requesting an instance of resource type Rj must have released any resources Ri such that F(Ri) ≥ F(Rj).

    - 仍有 deadlock 發生的可能性，這個 protocol 需要 programmer 寫程式時遵守規則才可以 prevent deadlock



Deadlock avoidance
++++++++++++++++++

- requires that the operating system be given additional information in advance concerning which resources a process will request and use during its lifetime

- A deadlock-avoidance algorithm dynamically examines the resource-allocation state to ensure that a circular-wait condition can never exist.


**safe state**

- a system is in a safe state only if there exists a **safe sequence**. 

  - A sequence of processes <P1, P2, ..., Pn> is a safe sequence for the current allocation state if, for each Pi , the resource requests that Pi can still make can be satisfied by the currently available resources plus the resources held by all Pj , with j < i.



Algorithm
^^^^^^^^^

- Resource-Allocation-Graph Algorithm

  - claim edge

- Banker’s Algorithm

  - When a user requests a set of resources, the system must determine whether the allocation of these resources will leave the system in a safe state. If it will, the resources are allocated; otherwise, the process must wait until some other process releases enough resources
  
  
- Safety Algorithm
- Resource-Request Algorithm


7.6 Deadlock Detection
-----------------------


- Detection-Algorithm Usage



7.7 Recovery from Deadlock
--------------------------

- Process Termination

  - Abort all deadlocked processes
  - Abort one process at a time until the deadlock cycle is eliminated
  
    - incurs considerable overhead, since after each process is aborted, a deadlock-detection algorithm must be invoked 

- Resource Preemption

  - Selecting a victim
  - Rollback
  - Starvation

