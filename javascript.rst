===========
Javascript
===========

Error
++++++++
[Violation] Added non-passive event listener to a scroll-blocking 'mousewheel' event. Consider marking event handler as 'passive' to make the page more responsive.

Sol.


`chrome - 網站使用被動事件偵聽器以提升滾動性能 <https://developers.google.com/web/tools/lighthouse/audits/passive-event-listeners?hl=zh-tw>`_

`JQuery: Consider adding support for passive event listeners <https://github.com/jquery/jquery/issues/2871>`_

我略看了一下大概是 JQuery 目前還沒有支援 passive event listeners，如果想解這部分目前看來有兩種方式

1. 使用 `GitHub : default-passive-events <https://github.com/zzarcon/default-passive-events>`_
讓 console 直接不顯示這個 warning

2. 使用原生 Javascript 改寫這部分的 binding


[ref] 
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






