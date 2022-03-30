RTOS
=======

.. raw:: html

    <img src="https://i.imgur.com/UJLNPZu.png" width="800px">
    
|

ISR

- x86 => 80h
  
  - uC/OS 在 80 號註冊一個 ISR
  - 自己 trigger 80 號: 自己把 CPU 讓出來
  



|

Ready --- Scheduler ---> Running

|

- ``OSStart()``

  - 第一次把 CPU 交出去
  - 把 CPU 交給第一個 Task，看誰的 priority 最高

|

- ``OS_Task_SW()``

  - 自己 trigger 一個軟體中斷，專門做 context switch
  - 有 Task 想要把 CPU 主動交出
  - 會有一個 Task 從 Ready -> Running

|

- ``OSIntExt()``
  
  - Preemption
  - 被搶先
  - 中斷(Interrupt)離開的時候


|

Context Switch
----------------

Overhead

- 執行時間要再加兩倍 context switch 時間

.. image:: https://i.imgur.com/Au9QPFV.png


Kernel
--------

uC/OS 的 kernel 做的事情很少


- Task Management

  - Scheduling

- IPC

  - mutex lock









