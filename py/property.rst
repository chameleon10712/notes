Property
==========

.. code:: python

  class Bank_acount:
      def __init__(self):
          self._password = ‘預設密碼 0000’

      @property
      def password(self):
          return self._password

      @password.setter
      def password(self, value):
          self._password = value

      @password.deleter
      def password(self):
          del self._password
          print('del complite')

