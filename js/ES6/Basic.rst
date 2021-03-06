ES6
===

Object Literal Property Value Shorthand
---------------------------------------

ES5 

.. code-block:: javascript

  function createMonster(name, power) {
    return { type: 'Monster', name: name, power: power };
  }
  function createWitch(name) {
    return { type: 'Witch', name: name };
  }


ES6 shorthand

.. code-block:: javascript

  function createMonster(name, power) {
    return { type: 'Monster', name, power };
  }
  function createWitch(name) {
    return { type: 'Witch', name };
  }

`[ref] <https://ariya.io/2013/02/es6-and-object-literal-property-value-shorthand>`_





Const
-----

宣告 ``const`` 會對於它的值建立一個唯讀的參考。並不是說這個值不可變更，而是這個變數不能再一次指定值。例如，假設常數的內容(值)是個物件，那麼此物件的內容(物件的參數)是可以更改的。


.. code-block:: javascript

  const number = 42;

  try {
    number = 99;
  } catch(err) {
    console.log(err);
    // expected output: TypeError: invalid assignment to const `number'
    // Note - error messages will vary depending on browser
  }

  console.log(number);
  // expected output: 42



let
---

``let`` 用於宣告一個「只作用在當前區塊的變數」，初始值可選擇性的設定。

.. code-block:: javascript

  let x = 1;

  if (x === 1) {
    let x = 2;

    console.log(x);
    // expected output: 2
  }

  console.log(x);
  // expected output: 1




Default parameters
------------------

**Default function parameters** allow named parameters to be initialized with default values if no value or ``undefined`` is passed.


.. code-block:: javascript

  function multiply(a, b = 1) {
    return a * b;
  }

  console.log(multiply(5, 2));
  // expected output: 10

  console.log(multiply(5));
  // expected output: 5



Template literals (Template strings)
-------------------------------------

樣板字面值（Template literals）被反引號（back-tick，重音符號）：` ` 字元封閉，代替了雙或單引號。樣板字面值可以包含由錢字元及花括號所構成（${expression}） 的佔位符（placeholders）。


.. code-block:: javascript

  `string text`

  `string text line 1
   string text line 2`

  `string text ${expression} string text`

  tag `string text ${expression} string text`


Class
-----

ES 6 中引入了類別 (class) 作為 JavaScript 現有原型程式(prototype-based)繼承的語法糖。類別語法並 **不是** 要引入新的物件導向繼承模型到 JavaScript 中，而是提供一個更簡潔的語法來建立物件和處理繼承。


Class Declaration
^^^^^^^^^^^^^^^^^

.. code-block:: javascript

  class Polygon {
    constructor(height, width) {
      this.height = height;
      this.width = width;
    }
  }


Hoisting
++++++++

**函數宣告 (function declarations)** 和 **類別宣告 (class declarations)** 的一個重要差別在於函數宣告是 `hoisted <https://developer.mozilla.org/zh-TW/docs/Glossary/Hoisting>`_ ，類別宣告則不是。 你需要先宣告你的類別，然後存取它，否則像是下面的程式碼就會丟出一個 ``ReferenceError``:

.. code-block:: javascript

  var p = new Polygon(); // ReferenceError

  class Polygon {}



Class Expression
^^^^^^^^^^^^^^^^^

.. code-block:: javascript

  // unnamed
  var Polygon = class {
    constructor(height, width) {
      this.height = height;
      this.width = width;
    }
  };

  // named
  var Polygon = class Polygon {
    constructor(height, width) {
      this.height = height;
      this.width = width;
    }
  };







Import
------

**import** 宣告用於引入由另一個模塊所導出的綁定。被引入的模塊，無論是否宣告``strict mode``，都會處於該模式。``import`` 宣告無法用於嵌入式腳本（embedded scripts）。


The static ``import`` statement is used to import bindings which are exported by another module. Imported modules are in ``strict mode`` whether you declare them as such or not. The import statement cannot be used in embedded scripts unless such script has a ``type="module"``.



.. code-block:: javascript

  import defaultExport from "module-name";
  
  import * as name from "module-name";
  
  import { export } from "module-name";
  
  import { export as alias } from "module-name";
  
  import { export1 , export2 } from "module-name";
  
  import { export1 , export2 as alias2 , [...] } from "module-name";
  
  import defaultExport, { export [ , [...] ] } from "module-name";
  
  import defaultExport, * as name from "module-name";
  
  import "module-name";







