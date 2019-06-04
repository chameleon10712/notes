Main Memory
===========

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

