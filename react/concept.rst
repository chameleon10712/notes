React
=====



bind() in class component
--------------------------

This is why we need to bind event handlers in Class Components in React `[Blog] <https://www.freecodecamp.org/news/this-is-why-we-need-to-bind-event-handlers-in-class-components-in-react-f7ea1a6f93eb/>`_


`[codepen] <https://codepen.io/gaearon/pen/xEmzGg?editors=0010>`_

.. code:: jsx

  class Toggle extends React.Component {
    constructor(props) {
      super(props);
      this.state = {isToggleOn: true};

      // 為了讓 `this` 能在 callback 中被使用，這裡的綁定是必要的：
      this.handleClick = this.handleClick.bind(this);
    }

    handleClick() {
      this.setState(state => ({
        isToggleOn: !state.isToggleOn
      }));
    }

    render() {
      return (
        <button onClick={this.handleClick}>
          {this.state.isToggleOn ? 'ON' : 'OFF'}
        </button>
      );
    }
  }


|

或者使用另一種寫法 (使用 arrow function)

.. code:: jsx

  class LoggingButton extends React.Component {
    // 這個語法確保 `this` 是在 handleClick 中被綁定：
    // 警告：這是一個還在*測試中*的語法：
    handleClick = () => {
      console.log('this is:', this);
    }

    render() {
      return (
        <button onClick={this.handleClick}>
          Click me
        </button>
      );
    }
  }

  ReactDOM.render(
    <Toggle />,
    document.getElementById('root')
  );


