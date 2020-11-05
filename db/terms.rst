Terms
========

- Denormalization

  - Denormalization is a strategy used on a previously-normalized database to increase performance. 
    In computing, denormalization is the process of trying to improve the read performance of a database, 
    at the expense of losing some write performance, by adding redundant copies of data or by grouping data. `[ref] <https://en.wikipedia.org/wiki/Denormalization>`_
    
  - `知乎 - Database 與 Datawarehouse 的本質區別是什麼？ <https://www.zhihu.com/question/20623931/answer/750367153>`_

|

- SQL Constraint 限制

  - Constraint 用來有條件地限制哪些資料才可以被存入資料表中，也就是對欄位作約束
  - ex.
  
    - NOT NULL 非空值限制
    - UNIQUE 唯一限制
    - PRIMARY KEY 主鍵限制
    - FOREIGN KEY 外鍵限制
    - CHECK 檢查限制
    - DEFAULT 預設值限制
    
  - `ref <https://www.fooish.com/sql/constraints.html>`_
 
|

- CASCADE

  - `What does on_delete do on Django models? <https://stackoverflow.com/a/38389488>`_
