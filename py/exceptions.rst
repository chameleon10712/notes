Exceptions
============


- `[Python教學]掌握重要的Python例外處理機制  <https://www.learncodewithmike.com/2019/12/python-exceptions.html>`_



- `[python document] Built-in Exceptions <https://docs.python.org/3/library/exceptions.html>`_


|


User-defined Exceptions
--------------------------

- `python tutorial doc <https://docs.python.org/3/tutorial/errors.html#user-defined-exceptions>`_


- Exceptions should typically be derived from the Exception class, either directly or indirectly.
- When creating a module that can raise several distinct errors, a common practice is to create a base class for exceptions defined by that module, and subclass that to create specific exception classes for different error conditions


.. code:: py

  class Error(Exception):
      """Base class for exceptions in this module."""
      pass

  class InputError(Error):
      """Exception raised for errors in the input.

      Attributes:
          expression -- input expression in which the error occurred
          message -- explanation of the error
      """

      def __init__(self, expression, message):
          self.expression = expression
          self.message = message

  class TransitionError(Error):
      """Raised when an operation attempts a state transition that's not
      allowed.

      Attributes:
          previous -- state at beginning of transition
          next -- attempted new state
          message -- explanation of why the specific transition is not allowed
      """

      def __init__(self, previous, next, message):
          self.previous = previous
          self.next = next
          self.message = message


