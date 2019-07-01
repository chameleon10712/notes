CSS
===

CSS Selector to get the element attribute value

.. code:: sh

  $ scrapy shell index.html
  >>> response.css('td.hey a:nth-child(1)::attr(href)').extract()
  [u'https://example.com']


``index.html``

.. code:: html

  <table>
      <tr>
          <td class='hey'>
              <a href="https://example.com">Fist one</a>
          </td>
      </tr>
  </table>


`[ref] <https://stackoverflow.com/a/24987710/5427571>`_



