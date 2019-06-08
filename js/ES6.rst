ES6
===

Destructuring Assignment
------------------------

解構賦值 (Destructuring Assignment) 是一種 JavaScript 運算式，可以將陣列或物件中的資料取出成獨立變數。


.. code-block:: javascript
  
  var a, b, rest;
  [a, b] = [10, 20];

  console.log(a);
  // expected output: 10

  console.log(b);
  // expected output: 20

  [a, b, ...rest] = [10, 20, 30, 40, 50];

  console.log(rest);
  // expected output: [30,40,50]



Object destructuring
^^^^^^^^^^^^^^^^^^^^

.. code-block:: javascript

  var o = {p: 42, q: true};
  var {p, q} = o;

  console.log(p); // 42
  console.log(q); // true


Assigning to new variable names
++++++++++++++++++++++++++++++++

.. code-block:: javascript

  var o = {p: 42, q: true};
  var {p: foo, q: bar} = o;

  console.log(foo); // 42 
  console.log(bar); // true


Default values
+++++++++++++++

.. code-block:: javascript

  var {a = 10, b = 5} = {a: 3};

  console.log(a); // 3
  console.log(b); // 5




Const
-----

Constants (常數) 有點像使用 ``let`` 所宣告的變數，具有區塊可視範圍。常數不能重複指定值，也不能重複宣告。

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

ES 6 中引入了類別 (class) 作為 JavaScript 現有原型程式(prototype-based)繼承的語法糖。類別語法並**不是**要引入新的物件導向繼承模型到 JavaScript 中，而是提供一個更簡潔的語法來建立物件和處理繼承。


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

**函數宣告 (function declarations)** 和 **類別宣告 (class declarations)** 的一個重要差別在於函數宣告是 ``hoisted <https://developer.mozilla.org/zh-TW/docs/Glossary/Hoisting>``_ ，類別宣告則不是。 你需要先宣告你的類別，然後存取它，否則像是下面的程式碼就會丟出一個 ``ReferenceError``:

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







