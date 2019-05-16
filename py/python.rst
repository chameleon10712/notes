===============
    Python
===============

**Sort list of dictionaries by another list**
::

	list = [{
		"id": "a", 
		"name": "xxx", 
		"attr": "val1"
	 }, 
	 {
		"id": "b", 
		"name": "yy", 
		"attr": "val2"
	 }, 
	 {
		"id": "c", 
		"name": "zzz", 
		"attr": "val3"
	 }]

	order = ['b','c','a']

Sol. ::

	sorted(list,key=lambda x:order.index(x['id']))


**How to sort a list according to another list?** 

`[ref] <https://stackoverflow.com/questions/12814667/how-to-sort-a-list-according-to-another-list>`_ 

Sort a according to b ::

	a = [("ax", 1), ("ec",3), ("bk", 5)]
	b = ["ec", "ax", "bk"]

Sol. 1 ::

	a.sort(key=lambda x: b.index(x[0]))
	
Sol. 2 ::

	a.sort(key=lambda (x,y): b.index(x))

Large List ::

	mapping = dict(a)
	a[:] = [(x,mapping[x]) for x in b]
	
Arbitrary-length tuples::

	mapping = dict((x[0], x[1:]) for x in a)
	a[:] = [(x,) + mapping[x] for x in b]
 
 
 
------------------
	lambda	
------------------

>>> list = [{'enabled': 'no', 'Name': 'data', 'rotation': '4', 'often': 900}ame': 'data2', 'rotation': '5', 'often': 86400}]
>>> 
>>> sorted(list,key = lambda often: often['often'])
[{'enabled': 'no', 'Name': 'data', 'often': 900, 'rotation': '4'}, {'Name': 'data2', 'often': 86400, 'rotation': '5'}]



>>> lambda x: x**2
<function <lambda> at 0x80072cbf8>
>>> (lambda x: x**2)(3)
9
>>> f = (lambda x: x**2)
>>> f
<function <lambda> at 0x80072cbf8>
>>> f(5)
25


-----------------------
	string format		
-----------------------

>>> '{}/{}'.format('backup_pool',name)
'backup_pool/data'

-----------------------
	subprocess
-----------------------
Python 3.5 以上支援


>>> import subprocess
>>> subprocess.run('ls')
<filename>.tar	daemon		HW2		sahw2-check.sh	timer.py
>>> subprocess.run(['ls','-l'])



-------------
  file io
-------------
>>> fo = open("zbackup.conf","r")
>>> next(fo)
'#zbackup.conf\n'
>>> next(fo)
'\n'
>>> next(fo)
'[backup_pool/data]\n'

------------
 search
------------
>>> import re
>>> m = re.search('\w+/\w+','[zroot/data]')
>>> m.group(0)
'zroot/data'

-----------------------
 match
-----------------------
>>> import re
>>> m = re.match(r"\[(\w+)/(\w+)\]","[zroot/data]")
>>> m.group(0)
'[zroot/data]'
>>> m.group(1)
'zroot'
>>> m.group(2)
'data'

-----------------------
	time stamp
-----------------------

>>> import time
>>> time.time()
1482580337.6782422
>>> time.time()
1482580340.361458

-----------------------
    others
-----------------------
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


