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

Asynchronous Module Definition，是Common JS所定義的一組優雅且簡單API，用於同步或非同步載入Javascript Module和它所依賴的其他Module，
而Require JS就是一套很著名且已經實作這組API的Library。它特別適合使用於解決瀏覽器使用同步(Synchronous)載入所導致的效能、可使用性、測試和Cross Domain等問題。

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
CommonJS
=========
CommonJS是一套規範，它的創建和核准是開放的。這個規範已經有很多版本和具體實現。CommonJS並不是屬於ECMAScript TC39小組的工作，但TC39中的一些成員參與CommonJS的製定。2013年5月，Node.js的包管理器NPM的作者Isaac Z. Schlueter說CommonJS已經過時，`Node.js的內核開發者已經廢棄了該規範
<https://github.com/nodejs/node-v0.x-archive/issues/5132#issuecomment-15432598>`_。

==========
TypeScript
==========

- 完全基於 JavaScript 語法

由於 JavaScript 的語法 (嚴格來講是 ECMAScript 262 3/e 或 5/e) 在 typing (資料型別) 上沒有很完美的解決方案，而且又有一些眉眉角角跟幾個大家熟悉的程式語言（如：C/C++、Java、C# 等）習慣不同，所以要使用 JavaScript 開發大型的應用程式，必須要有很小心的規範以及開發人員必須很深入瞭解 JavaScript 的「good/ugly/awful parts」（參考：JavaScript: The Good Parts）。

所以一直以來都有各式各樣的 project 想要改善這個問題（參考這裡有人整理了一個列表），最常被大家提到的就像 GWT (Google Web Toolkit) 、Script# 或是 CoffeeScript，它們都希望減輕 JavaScript 開發人員的負擔，改用一些結構良好或是更輕鬆的語言來開發應用程式（GWT 是 Java、Script# 是 C# 而 CoffeeScript 則是自定的語法），再透過各自的編譯器（compiler）來產出 JavaScript 程式碼。這些 projects 各有各的優缺點，也有其市場（減低語言轉換成本），乍看之下 TypeScript 好像也是在做類似的事，但它與上述提到的這些 project 不同的地方在於：它完全相容 JavaScript 原本的語法。也就是如果你過去剛好是一位 JavaScript developer，你可以在不改變過去撰寫 JavaScript 的習慣繼續撰寫程式，如同 TypeScript 官網上的範例 `[ref] <https://blogs.msdn.microsoft.com/ericsk/2012/10/01/typescript/>`_

.. code:: javascript

 function greeter(person) {
     return "Hello, " + person;
 }

 var user = "Jane User";

 document.body.innerHTML = greeter(user);

- 加入靜態型別

=======
  JSX
=======

--------------
使用 JSX 的好處
--------------

1. 提供更加語意化且易懂的標籤

   .. code:: javascript

    <form class="messageBox">
      <textarea></teextarea>
      <button type="submit"></button>
    </from>

   以 Facebook 上面按讚功能來說，若是命令式 Imperative 寫法大約會是長這樣：

   .. code:: javascript

    if(userLikes()) {
      if(!hasBlueLike()) {
        removeGrayLike();
        addBlueLike();
      }
    } else {
      if(hasBlueLike()) {
        removeBlueLike();
        addGrayLike();
      }
    }


   若是聲明式 Declarative 則是會長這樣：

   .. code:: javascript

    if(this.state.liked) {
      return (<BlueLike />);
    } else {
      return (<GrayLike />);
    }

2. 更加簡潔
3. 結合原生 JavaScript 語法

`[TechBridge] <https://blog.techbridge.cc/2016/04/21/react-jsx-introduction/>`_




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

`Webpack Howto GitHub <https://github.com/petehunt/webpack-howto>`_

