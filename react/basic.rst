Usage
=====


Inline Style

.. code:: javascript

  const divStyle = {
    color: 'red',
    backgroundImage: 'url(' + imgUrl + ')',
  };

  ReactDOM.render(<div style={divStyle}>Hello World!</div>, document.getElementById('app'));


or


.. code:: javascript

  ReactDOM.render(
    <div style={{ fontWeight: 'bold' }}>Hello World!</div>,
    document.getElementById('app')
  );


