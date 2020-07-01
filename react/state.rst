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


|

Life Cycle
-------------

加入生命週期方法到 Class






