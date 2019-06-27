JS fetch 

.. code:: javascript

  let myHeaders = new Headers({
      'Access-Control-Allow-Origin': '*',
      'Content-Type': 'text/plain'
  });

  fetch(url, {
      method: 'GET',
      mode: 'no-cors'
  }) .then((res) => {
      console.log('res', res);
  })

`[知乎] <https://www.zhihu.com/question/47029864>`_









