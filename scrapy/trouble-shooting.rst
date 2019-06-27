twisted.python.failure.Failure
==============================


被目標 server block request 時的錯誤訊息

.. code:: sh

  twisted.python.failure.Failure twisted.internet.error.ConnectionDone: Connection was closed cleanly


Solution
--------

設定 ``settings.py`` 假裝自己是 browser 發送 request


``USER_AGENT = 'Mozilla/5.0 (Windows NT 6.3; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/37.0.2049.0 Safari/537.36'``

|


Random 你的 Browser 資訊
-----------------------

`user-agent randomiser <https://github.com/cnu/scrapy-random-useragent>`_

 

|


ref
---

`[StackOverflow] <https://stackoverflow.com/questions/30028585/how-to-prevent-a-twisted-internet-error-connectionlost-error-when-using-scrapy>`_
