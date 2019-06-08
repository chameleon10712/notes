ES5
===

Strict Mode
------------

ECMAScript 5 提供開發者語法嚴格、語法受限的模式 (strict mode) ，會影響語法的使用但沒支援受限模式的瀏覽器一樣可以跑，只是行為有很大的可能會跟你想的不一樣。所以別太依賴受限模式，除非你做過功能性測試。另外這個模式可以混用在普通模式裡，你可以利用這個特性慢慢把舊的程式碼轉變成完全嚴謹和低變化性的狀態。

這個模式裡做了些語意上的修正:

1. 透過拋出錯誤的方式消除一些安靜的錯誤（意指不再靜默地忽略某些錯誤）
2. 修正會阻礙 JavaScript 引擎進行最佳化的錯誤: 相同的程式碼在嚴格模式有時候能運行得比非嚴格模式來的快
3. 禁止使用一些有可能被未來版本 ECMAScript 定義的語法

參考 `過渡到嚴格模式 <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode/Transitioning_to_strict_mode>`_，如果你希望將你的程式碼在  JavaScript 語法嚴格、語法受限下執行。

.. code:: javascript

  // Whole-script strict mode syntax
  
  'use strict';
  
  var v = "Hi! I'm a strict mode script!";


`[ref] <https://developer.mozilla.org/zh-TW/docs/Web/JavaScript/Reference/Strict_mode>`_















