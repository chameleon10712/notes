===================
    Front-End     
===================


=================
    AMD 規範    
=================


Asynchronous Module Definition，是Common JS所定義的一組優雅且簡單API，

用於同步或非同步載入Javascript Module和它所依賴的其他Module，

而Require JS就是一套很著名且已經實作這組API的Library。

它特別適合使用於解決瀏覽器使用同步(Synchronous)載入所導致的效能、可使用性、測試和Cross Domain等問題。

AMD的API主要格式如下 

``define(id?, dependencies?, factory);``

id 代表Module的名稱
dependencies 代表Module所依賴的其他Module
factory 代表產生Module的工廠(Factory)或是它的實體(Object)


`AMDJS.api
<https://github.com/amdjs/amdjs-api/wiki/AMD/>`_

-----------
AMD Library
-----------

- Require JS
- Curl




`ref
<https://dotblogs.com.tw/kirkchen/2012/06/20/javascript_amd_introduction/>`_

