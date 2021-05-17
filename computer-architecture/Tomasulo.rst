Tomasulo's Algorithm
========================



.. code:: py

  div.d F0, F1, F2
  add.d F3, F0, F4 #F0 depend on previous instr
  sub.d F12, F10, F11


如果在 div.d 與 add.d 之間加 stall 的話，後面的 sub.d 也會跟著受影響

狀況類似於，如果今天是單行道的話，前面的車停了，後面的車子也要跟著停

=> 如果使用雙線道呢？

|

Tomasulo's Algorighm
-------------------------

RS: reservation station


Tomasulo Pipeline Phases
--------------------------

- IF

  - fetch next instr into FIFO queue of pending instructions

- Issue

  - get next instr from queue
  - if matching RS free (no structural hazard), issue instr to RS
  
    - w/ operand values if they are currently in registers
    - otherwise, w/ identifiers of RSs that will produce operands
    
    
- Execution

  - when all operands available (no RAW) and FU (Functional Unit) free, execute
  - if not, monitor CDB (common data bus) for result

- Write result

  - write result on CDB to all awaiting stations and register file
  - mark RS free
















|
|

Reference

- `YouTube - Dynamic Scheduling Using Tomasulo's Algorithm <https://www.youtube.com/watch?v=y-N0Dsc9LmU>`_


