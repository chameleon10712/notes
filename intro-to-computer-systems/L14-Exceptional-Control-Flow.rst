Exceptional Control Flow: Exceptions and Processes
=====================================================

CMU - Intro to Computer Systems, Fall 2016

- `[schedule] <http://www.cs.cmu.edu/afs/cs/academic/class/15213-f16/www/schedule.html>`_

- `[video] <https://scs.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=d2759175-d59e-4f80-ab9e-24c2f15c8adb>`_
- `[slide] <http://www.cs.cmu.edu/afs/cs/academic/class/15213-f16/www/lectures/14-ecf-procs.pdf>`_


Control Flow
--------------

- control flow
  
  - sequence of instruction

- physical control flow

  - the actual sequence of instruction that the hardware is executing

|

Alerting Control Flow
------------------------

- branch and jumps
- call and return

react to change of ``program state``

|

但是這些不足以應付 ``system state`` 的改變

- system state

  - e.g. ``Ctrl-C``, 除以零, system timer expires, data arrives from a disk or a network adapter


-> system 需要 ``exceptional control flow`` (ECF)

|

Exceptional Control Flow
----------------------------


- low level
  
  - Exceptions
  
    - change in ``system state``
    - 實作上需要 hardware & OS software

- high level

  - Process Context Switch
  - Signals
  - Nonlocal jumps: ``setjmp()`` and ``longjmp()``
  
  
|
  
Exceptions
-------------

Exception: user code -> kernel code

|

- ECF (Exceptional Control Flow)

  - Asynchronous
    
    - 由 processor 之外的 event 所造成
    - Interrupts
      
      - Timer Interrupt, IO Interrupt (Ctrl+C)
      
  |
  - Synchronous
  
    - 執行指令後造成的 event

    - Traps
      
      - intentional
      - ``system call``, breakpoint trap, special instructions
       
    - Faults
    
      - unintentional but possibly recoverable
      - page faults (memory), protection faults, floating point exceptions
      
    - Aborts

      - unintentional and unrecoverable
      - illegal instruction, parity error, machine check


  
