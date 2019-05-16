============================
	Basic Command Line	
============================

rename directory  ``mv /home/user/oldname /home/user/newname``

find file  ``find -iname <filename>``


======================
	  好用參數
======================
``!!`` 上一個指令::

	ntpdate -b pool.ntp.org
	sudo !!


``!$`` 上一個指令的最後一個參數::

	mkdir complicated-folder-name
	cd !$


``ls -1`` 一個file/dir一行

數當前目錄有多少個files & directory  ``ls -1 | wc -l``

``ls -t1 /backup_pool/data``  以時間 sort file ，由早到晚 

``ls -tr1 /backup_pool/data``  以時間 sort file ，由晚到早 

