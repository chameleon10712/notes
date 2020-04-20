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

Server Side
-------------

bind -> listen -> accept

listenfd (file descriptor): 對於 server 來說，每一個 client 都有一個自己的 file descriptor，藉由這樣的方式保持與不同 client 之間的連線 


