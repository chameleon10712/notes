State
========

1:09:49 - Mosh


.. code:: jsx

  class Counter extends Component {

    state = {
      count: 0
    };

    handleIncrement = () => {
      this.state.count++; // doesn't work
    };
    
    // ...
  }



.. code:: jsx

  class Counter extends Component {

    state = {
      count: 0
    };

    handleIncrement = () => {
      setState({count: this.state.count + 1}) // react is aware of the change of the state
    };  
    
    // ...

  }

|

State  v.s. Props
--------------------

State 類似於 prop，但它是私有且由 component 完全控制的。

component 被定義為 class 有一些額外的特性。Local state 就是 class 其中的一個特性。



state 和 props 有什麼不同？
+++++++++++++++++++++++++++

props（「properties」的簡寫）和 state 都是純 JavaScript object。雖然兩者都擁有會影響 render 輸出的資訊，但在一個重要方向上有所不同：props 是被傳遞進 component（類似於 function 的參數），而 state 是在 component 內部被管理（類似於在 function 中宣告中的變數）。


`[ref] <https://zh-hant.reactjs.org/docs/faq-state.html>`_


|


SetState
-----------

setState() 安排對 component state object 的更新。當 state 改變時，component 會藉由重新 render 來回應。


State Updates May Be Asynchronous
++++++++++++++++++++++++++++++++++++++++

State 的更新可能是非同步的



setState 何時是非同步？
***********************

目前 setState 在 event handler 中是非同步。

這會確保 Child 不會重新 render 兩次，像是 Parent 和 Child 在一個單次 click 事件中同時呼叫 setState 的例子。取而代之，React 會在瀏覽器事件結束時「刷新」state 的更新。這在大型應用程式中能產生顯著的效能提升。

這是一個實作細節所以請避免直接依懶它。未來的版本中，React 將在更多情況下預設批次處理更新。




|

Lifecycle
-------------

加入生命週期方法到 Class

|


.. image:: https://iandays.com/images/react-life.png



|

Reference
------------

react doc - `State 和生命週期 <https://zh-hant.reactjs.org/docs/state-and-lifecycle.html>`_


