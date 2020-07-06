Concurrency Control Theory
=============================


- `[Schedule] <https://15445.courses.cs.cmu.edu/fall2018/schedule.html>`_
- `[Video] <https://www.youtube.com/watch?v=r0nI_yV9KCo&list=PLSE8ODhjZXja3hgmuwhf89qboV1kOxMx7&index=16>`_
- `[Slide] <https://15445.courses.cs.cmu.edu/fall2018/slides/16-concurrencycontrol.pdf>`_
- `[Notes] <https://15445.courses.cs.cmu.edu/fall2018/notes/16-concurrencycontrol.pdf>`_
- Readings: Chapter 14

|

CORRECTNESS CRITERIA: ACID

- Atomicity

  - all or none

- Consistency

  - correct

- Isolation

  - transaction 在實際被執行時可能被拆為好幾個 action, 確保 transaction 在執行時不被干擾即是 isolation

- Durability

  -  a transaction’s actions must persist across crashes






