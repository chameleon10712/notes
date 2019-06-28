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



Replace parts of a string with JSX

.. code:: javascript

    let s = 'this is your sentence'
    let w = 'your' // target word
    let r = new RegExp(`\(${word}\\w*\)`, 'gi')
    s = s.split(r)
    s = <div>{s[0]}<span className='target'>{s[1]}</span>{s[2]}</div>
    
    // <div>this is <span className='target'>your</span>sentence</div>












