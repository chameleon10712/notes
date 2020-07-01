State
========

1:09:49 - Mosh

react doc - `State 和生命週期 <https://zh-hant.reactjs.org/docs/state-and-lifecycle.html>`_


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

Life Cycle
-------------

加入生命週期方法到 Class






