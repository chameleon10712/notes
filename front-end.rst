=========
Front-End
=========

- AMD
- CMD
- CommonJS

- gulp
- browserify

- JSX
- Coffee Script
- TypeScript

- webpack

- production-ready

=====
 AMD 
=====

--------
AMD 規範 
--------

Asynchronous Module Definition，是Common JS所定義的一組優雅且簡單API，

用於同步或非同步載入Javascript Module和它所依賴的其他Module，

而Require JS就是一套很著名且已經實作這組API的Library。

它特別適合使用於解決瀏覽器使用同步(Synchronous)載入所導致的效能、可使用性、測試和Cross Domain等問題。

AMD的API主要格式如下 

``define(id?, dependencies?, factory);``

id 代表Module的名稱
dependencies 代表Module所依賴的其他Module
factory 代表產生Module的工廠(Factory)或是它的實體(Object) `[ref]
<https://dotblogs.com.tw/kirkchen/2012/06/20/javascript_amd_introduction/>`_


`AMDJS.api
<https://github.com/amdjs/amdjs-api/wiki/AMD/>`_

-----------
AMD Library
-----------

- Require JS
- Curl

=====
 CMD
=====

`[CMD spec]
<https://github.com/cmdjs/specification/blob/master/draft/module.md>`_

===============
AMD 和 CMD 區別
===============
`[知乎]
<https://www.zhihu.com/question/20351507>`_




=========
 Webpack
=========
Webpack 是德國開發者 Tobias Koppers 開發的模組整合工具。它的核心功能如下:

- 可同時整合 CommonJS 和 AMD 模組
- 轉換 JSX, Coffee Script, TypeScript 等
- 分散封裝專案使用的程式碼，使載入頁面時只需載入當頁所需的程式碼以加速載入速度
- 整合樣式表 (css, sass, less 等)
- 處理圖片與字型
- 建置 production-ready 的程式碼 (壓縮)


`如何使用 Webpack 模組整合工具
<https://rhadow.github.io/2015/03/23/webpackIntro/>`_


