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





