Main Memory
===========


8.1 Background
^^^^^^^^^^^^^^


8.1.1 Basic Hardware
--------------------

To make sure that each process has a separate memory space

- base register

  - holds the smallest legal physical memory address

- limit register

  - specifies the size of the range

|

Protection of memory space is accomplished by having the CPU hardware compare every address generated in user mode with the registers. 


The base and limit registers can be loaded only by the operating system,
which uses a special privileged instruction. Since privileged instructions can
be executed only in kernel mode, and since only the operating system executes
in kernel mode, only the operating system can load the base and limit registers.



8.1.2 Address Binding
---------------------

- input queue

  - The processes on the disk that are waiting to be brought into memory for execution form the input queue


The normal single-tasking procedure is to select one of the processes
in the input queue and to load that process into memory. As the process
is executed, it accesses instructions and data from memory. Eventually, the
process terminates, and its memory space is declared available


Addresses may be represented in different ways during these steps. Addresses in the source
program are generally symbolic (such as the variable count). A compiler
typically binds these symbolic addresses to relocatable addresses (such as
“14 bytes from the beginning of this module”). The linkage editor or loader
in turn binds the relocatable addresses to absolute addresses (such as 74014).
Each binding is a mapping from one address space to another.

Classically, the binding of instructions and data to memory addresses can
be done at any step along the way:

- Compile time
- Load time

  - If it is not known at compile time where the process will reside in memory, then the compiler must generate relocatable code

- Execution time


8.1.3 Logical Versus Physical Address Space
-------------------------------------------

- memory-management unit (MMU)



8.1.4 Dynamic Loading
---------------------

Dynamic loading

- a routine is not loaded until it is called
- useful when large amounts of code are needed to handle infrequently occurring cases, such as error routines
-  does not require special support from the os
- OS may help the programmer,however, by providing library routines to implement dynamic loading


8.1.5 Dynamic Linking and Shared Libraries
------------------------------------------

- `[linking] <https://en.wikipedia.org/wiki/Linker_(computing)>`_
- Dynamic Linking
- static linking

|

- Dynamically linked libraries

  - system libraries that are linked to user programs when the programs are run (refer back to Figure 8.3)


- stub

  - The stub is a small piece of code that indicates how to locate the appropriate memory-resident library routine or how to load the library if the routine is not already present
