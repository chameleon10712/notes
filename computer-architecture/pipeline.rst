Scheduling Branch Delay Slot
================================

- Compiler fills the delay slot


1. Delay slot scheduled w/ instr from **before** the branch

.. code:: py

    add r1, r2, r3
    beqz r2, L
    nop
    ...

  L:
  

.. code:: py

    beqz r2, L
    add r1, r2, r3



2. Delay slot scheduled from branch **target**


.. code:: py

   L: sub r4, r5, r6
      instr
      ...
      add r1, r2, r3
      beqz r1, L
      nop


.. code:: py

   L: instr
      ....
      add r1, r2, r3
      beqz r1, L
      sub r4, r5, r6





Reference

- `Scheduling Instructions for Branch Delay Slot <https://www.youtube.com/watch?v=vgMwKpp3L9o&list=PLeWkeA7esB-MuCn8XQWAarM7zvimE0yme&index=25>`_





