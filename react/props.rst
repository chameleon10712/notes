props
======

概念上來說，component 就像是 JavaScript 的 function，它接收任意的參數（稱之為「props」）並且回傳描述畫面的 React element。

.. code:: jsx

  function Welcome(props) {
    return <h1>Hello, {props.name}</h1>;
  }

  const element = <Welcome name="Sara" />;
  ReactDOM.render(element, document.getElementById('root'));

|


可以使用 javascript function (上方例子) 或者 ``ES6 Class`` 來定義 ``React Component``

.. code:: jsx

  class Welcome extends React.Component {
    render() {
      return <h1>Hello, {this.props.name}</h1>;
    }
  }


|

Component and Props
----------------------

|

.. code:: jsx

  function Welcome(props){
    console.log('props', props)
    return (
      <h1>
        Hello, {props.name}
        {props.id}
      </h1>
    );
  }

  function App() {
    return (
      <div>
        <Welcome name="Sara"  id="1" />
        <Welcome name="Cahal" id="2" />
        <Welcome name="Edite" id="3" />
      </div>
    );
  }

  ReactDOM.render(<App />, document.getElementById('root'));



Result

.. code::

  Hello, Sara1
  Hello, Cahal2
  Hello, Edite3


|

Props are Read-Only
+++++++++++++++++++++

不論使用 function 或是 class 來宣告 component，都絕不能修改自己的 props。



|

Reference

- `Reac Doc - Components 與 Props <https://zh-hant.reactjs.org/docs/components-and-props.html>`_




