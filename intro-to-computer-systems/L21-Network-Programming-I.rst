Network Programming Part I
============================

CMU - Intro to Computer Systems, Fall 2015

- `[schedule] <http://www.cs.cmu.edu/afs/cs/academic/class/15213-f16/www/schedule.html>`_

- `[video] <https://scs.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=54178cf8-d57e-4984-b46c-b66db645431a>`_
- `[slide] <http://www.cs.cmu.edu/afs/cs/academic/class/15213-f15/www/lectures/21-netprog1.pdf>`_

|

Hub & Switch
--------------

Hub 是無論接收到什麼封包都 broadcast

Switch , Router 則是會根據封包 metadata 選擇要傳給誰

|

Dotted Decimal Notation
--------------------------

Dotted Decimal Notation: IP address 的表示法

IP address: 0x8002C2F2 = 128.2.194.242  (80 對應到 128, 02 對應到 2, ...)



DNS
-----

``linux> nslookup www.twitter.com``



Internet Connections
-----------------------

- Socket: an endpoint of a connection

  - Socket address is an ``IPaddress:port`` pair
  - 對於 kernel 來說, socket 是溝通的端點
  - 對於 application 來說, socket 是一個 file descriptor, 用來讓 application 對網路進行讀寫
  
    - **All Unix I/O devices, including Networks, are modeled as files**
  
|

- Port: a 16-bit integer that identifies a process



|

Server Side
-------------

bind -> listen -> accept

listenfd (file descriptor): 對於 server 來說，每一個 client 都有一個自己的 file descriptor，藉由這樣的方式保持與不同 client 之間的連線 


