===============
    Python
===============

 


===========
  file io
===========
>>> fo = open("zbackup.conf","r")
>>> next(fo)
'#zbackup.conf\n'
>>> next(fo)
'\n'
>>> next(fo)
'[backup_pool/data]\n'

========
 search
========
>>> import re
>>> m = re.search('\w+/\w+','[zroot/data]')
>>> m.group(0)
'zroot/data'

=======
 match
=======
>>> import re
>>> m = re.match(r"\[(\w+)/(\w+)\]","[zroot/data]")
>>> m.group(0)
'[zroot/data]'
>>> m.group(1)
'zroot'
>>> m.group(2)
'data'

=====================
	time stamp
=====================

>>> import time
>>> time.time()
1482580337.6782422
>>> time.time()
1482580340.361458


==============
    others
==============
>>> for i,line in enumerate(fo):
...     print(i," ",line)
... 

0   #zbackup.conf
1   

2   [backup_pool/data]

3   enabled=no

4   policy=4x15m

5   

6   [backup_pool/data2]

7   policy=5x1d

8   

9  


