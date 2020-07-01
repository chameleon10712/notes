Install
=======



`ES7 React/Redux/GraphQL/React-Native snippets <https://marketplace.visualstudio.com/items?itemName=dsznajder.es7-react-js-snippets>`_

|



Basic Methods
==============


+------+--------------------------------------+
| imp→ | import moduleName from 'module'      |
+------+--------------------------------------+
| exp→ | export default moduleName            |
+------+--------------------------------------+
| nfn→ | const functionName = (params) => { } |
+------+--------------------------------------+
| met→ | methodName = (params) => { }         |
+------+--------------------------------------+



React Components
=================


``rcc``
 
.. code:: javascript
 
  import React, { Component } from 'react'

  export default class FileName extends Component {
    render() {
      return <div>$2</div>
    }
  }




``rce``

.. code:: javascript

  import React, { Component } from 'react'

  export class FileName extends Component {
    render() {
      return <div>$2</div>
    }
  }

  export default $1


``rfce``

.. code:: javascript

  import React from 'react'

  function $1() {
    return <div>$0</div>
  }

  export default $1




``rafc``

.. code:: javascript

  import React from 'react'

  const $1 = () => {
    return <div>$0</div>
  }

  export default $1



|

Other recommended extension

- `Simple React Snippets <https://marketplace.visualstudio.com/items?itemName=burkeholland.simple-react-snippets>`_

- `Prettier - Code formatter <https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode>`_

  - Mac vscode: code -> preference -> setting -> ... 
  - 8:55 Prettier formatter setting - `mosh video <https://www.youtube.com/watch?v=Ke90Tje7VS0>`_











