JS concurrency model
====================

JavaScript has a concurrency model based on an "event loop". This model is quite different from models in other languages like C and Java.

Event Loop
++++++++++

Run-to-completion

Adding messages

Zero delays

Several Runtime communicating together


Never blocking
++++++++++++++

A very interesting property of the event loop model is that JavaScript, unlike a lot of other languages, never blocks. Handling I/O is typically performed via events and callbacks, so when the application is waiting for an IndexedDB query to return or an XHR request to return, it can still process other things like user input. 














