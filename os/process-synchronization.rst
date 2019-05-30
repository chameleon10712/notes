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


