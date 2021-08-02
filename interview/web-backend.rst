Web Backend 面試題
===================

這一篇的主要訊息來自 

- `TechBridge - 2019 Web Backend 面試總結 <https://blog.techbridge.cc/2019/10/04/web-backend-interview-in-2019/>`_

|

OS
---

- Process v.s. Thread v.s. Coroutine
- Inter-Process Communication
- 調度策略（Scheduler）
- 死鎖（Deadlock）條件，以及如何解死鎖

|

網路 (Network)
---------------

- TCP 三次握手與四次揮手過程，為什麼要三次握手？為什麼要四次揮手？
- TCP v.s. UDP
- TCP 如何實現流量控制
- HTTP 有哪些狀態碼
- HTTP v.s. HTTPS
- HTTPS 加密過程
- HTTP v.s. HTTP2
- 瀏覽器打開網頁的過程

|

藉由網路相關考題，推薦一個面試技巧 - 如果兩個項目之間有演進關係，先說前一項技術遇到什麼問題，再說後一項技術怎麼解決。以「HTTP v.s. HTTPS」為例，不要只是回答「HTTPS 有加密」，而是先說明 HTTP 遇到什麼問題：

- 無法驗證身份
- 訊息沒加密
- 無法驗證訊息完整性
|

然後再說明後一項技術 HTTPS 如何解決這些問題：

- 非對稱加密 - 驗證身份
- 對稱加密 - 將訊息加密
- 雜湊（Hash）- 驗證訊息完整性



|

系統設計（System Design）
------------------------


- 工具箱類型

  - `極客時間 - 從 0 開始學架構 <https://time.geekbang.org/column/intro/81>`_

- 實戰練習

  - `Grokking the System Design Interview <https://www.educative.io/courses/grokking-the-system-design-interview>`_



|

特定軟體
---------

- Database

  - MySQL v.s. PostgreSQL
  - Index 有什麼好處？Database 怎麼做 Index？為什麼不要每個欄位都做 Index？
  - BTree v.s. B+Tree
  - SQL 相關的一些考題
  - MySQL 如何實現 Lock？
    - `[WikiBooks] MySQL/Lock <https://zh.m.wikibooks.org/zh-tw/MySQL/Lock>`_
  
- Memory Database
  - Redis v.s. Memcached
  - Redis 的 Sorted Set 如何實現？
  
- Nginx
  
  - Nginx 的實現原理是什麼？為什麼一台 Nginx Server 就可能撐上萬的 QPS (Queries-per-second)？


|


面試資源
--------
  
- `LeetCode Discuss <https://leetcode.com/discuss/interview-question>`_
- `一畝三分地 <https://www.1point3acres.com/bbs/forum-145-1.html>`_
- `掘金 <https://juejin.im/>`_

  - 試著搜尋「Python 面经」、用簡體搜尋
    
- 面試技巧、一般性問題

  - `Tech Interview Handbook <https://yangshun.github.io/tech-interview-handbook/questions-to-ask/>`_



Podcast List
--------------

`[ref] <https://www.ptt.cc/bbs/Soft_Job/M.1581283531.A.B75.html>`_


軟體工程或前端或 web 開發類的:

- Soft Skills Engineering
- The Complete Developer Podcast
- Software Defined Talk
- egghead.io developer chats
- IT Career Engergizer
- Syntax.fm
- Developer Tea
- The Bike Shed
- Changelog 出的全部 (直接搜 Changelog Master Feed)
- ShopTalk
- React Podcast
- User Error
- Merge Conflict

|

求職或職場類的 (有些聽聽就好):

- 7 Minute Job Interview Podcast
- The Ken Coleman Show
- How to be Awesome at Your Job
- Find Your Dream Job
- Safe For Work
- Dear HBR

|

雜談或其他類的:

- 4 Seas 1 Family
- The College Info Geek Podcast
- Abroard in Japan
- Negotiate Anything



