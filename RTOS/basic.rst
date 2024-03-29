RTOS
=======

.. raw:: html

    <img src="https://i.imgur.com/UJLNPZu.png" width="800px">
    
|

ISR



- x86 => 80h
  
  - uC/OS 在 80 號註冊一個 ISR
  - 自己 trigger 80 號: 自己把 CPU 讓出來
  - 軟體中斷
  



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

- ``OSIntExit()``
  
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

  - semaphore, mutex lock, message queue, mail box

- Memory Management

|

Kernel Romable?

- size 是不是夠小到可以塞到 ROM

|

RTOS Kernel

- 通常不超過 20K

|

Non-preemptive Scheduling
----------------------------

- Scheduler 設計簡單

- Task 與 Task 之間不會有 Race

  - 少數狀況下有 Race


- ex.

  - TinyOS


|

.. raw:: html

    <img src="https://i.imgur.com/hkz5oHs.png" width="800px">

|


Preemptive Scheduling
-------------------------

- ``OSIntExit()``


|

Nested Interrupt
-------------------

- ISR 有時候是 Nested 的
- 取決於作業系統, CPU 設計
- 一般來說，Interrupt 被允許是巢狀(Nested)的
  
  - uC/OS

- 有些不允許 Nested Interrupt

  - FreeRTOS

- 最後一個中斷離開的時候才需要做 context switch

|

Interrupt Latency
-------------------

Interrupt Disable

- Interrupt disable 只是暫時不理會訊號，等到 interrupt enable 後會繼續處理，中斷訊號不會不見









