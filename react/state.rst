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
      setState({count: this.state.count + 1}) // react is aware of the state change when using setState
    };  
    
    // ...

  }





