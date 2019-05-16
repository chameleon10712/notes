Javascript
===========

Strict Mode
+++++++++++

ECMAScript 5 提供開發者語法嚴格、語法受限的模式 (strict mode) ，會影響語法的使用但沒支援受限模式的瀏覽器一樣可以跑，只是行為有很大的可能會跟你想的不一樣。所以別太依賴受限模式，除非你做過功能性測試。另外這個模式可以混用在普通模式裡，你可以利用這個特性慢慢把舊的程式碼轉變成完全嚴謹和低變化性的狀態。

這個模式裡做了些語意上的修正:

1. 透過拋出錯誤的方式消除一些安靜的錯誤（意指不再靜默地忽略某些錯誤）
2. 修正會阻礙 JavaScript 引擎進行最佳化的錯誤: 相同的程式碼在嚴格模式有時候能運行得比非嚴格模式來的快
3. 禁止使用一些有可能被未來版本 ECMAScript 定義的語法






Error
++++++++
[Violation] Added non-passive event listener to a scroll-blocking 'mousewheel' event. Consider marking event handler as 'passive' to make the page more responsive.


`chrome - 網站使用被動事件偵聽器以提升滾動性能 <https://developers.google.com/web/tools/lighthouse/audits/passive-event-listeners?hl=zh-tw>`_

`JQuery: Consider adding support for passive event listeners <https://github.com/jquery/jquery/issues/2871>`_

Sol.
++++++++
我略看了一下大概是 JQuery 目前還沒有支援 passive event listeners，如果想解這部分目前看來有兩種方式

1.使用 `GitHub : default-passive-events <https://github.com/zzarcon/default-passive-events>`_
讓 console 直接不顯示這個 warning

2.使用原生 Javascript 改寫這部分的 binding


ref
++++++++
參考下列討論
https://github.com/angular/material2/issues/4221

了解詳細內容
`StackOverflow - Consider marking event handler as 'passive' to make the page more responsive <https://stackoverflow.com/questions/39152877/consider-marking-event-handler-as-passive-to-make-the-page-more-responsive>`_

`Chrome - Passive event listeners <https://www.chromestatus.com/feature/5745543795965952>`_





=============================
    Sortable.js Example
=============================

Using `Sortable.js <https://github.com/RubaXa/Sortable>`_
drag, save order :
`JSFiddle <https://jsfiddle.net/wpplugindev/53vhp34e/22/>`_






