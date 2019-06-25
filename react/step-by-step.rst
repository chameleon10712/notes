Before Coding
=============

1. Install `Create React App <https://github.com/facebook/create-react-app>`_

.. code:: sh

  npx create-react-app my-app
  cd my-app
  npm start


2. 

.. code:: sh

  cd my-app


3. Runs the app in development mode

.. code:: sh

  npm start



Start Coding
============


``src/index.js``


.. code:: javascript

  import React from 'react';
  import ReactDOM from 'react-dom';
  import './index.css';
  import App from './App';

  ReactDOM.render(<App />, document.getElementById('root'));



``src/App.js``

.. code:: javascript

  import React, { Component } from 'react';
  import './App.css'

  class App extends Component {

    state = {
      todos: [
        {title: 'first thing', id: 1},
        {title: 'second thing', id: 2}
      ]
    }

    addTodo = (todo) => {
      todo.id = Math.random();
      let todos = [...this.state.todos, todo];
      this.setState({
        todos: todos
      });
    }

    render() {
      return (
        <div className="App">
          ...
        </div>
      )
    }
  }

  export default App;






