==================
	shell script 
==================

+----------+-------------+------------+----------+----------+----------+
| sudo     |    sh       | test.sh    | aa       | bbb      | PPAP     |
+==========+=============+============+==========+==========+==========+
|                        | $0         | $1       | $2       | $3       |
+------------------------+------------+----------+----------+----------+

- $@ : aa bbb PPAP
- $# : 3


**shebang**::

	#!python
	#!/usr/bin/python
	#!/usr/local/bin/python
	#!/usr/bin/python -t


**指定這個檔案用sh 執行**::

	#!/bin/sh

``-f``  
The  shell  does not load any resource or startup files, or perform
any command hashing, and thus starts faster.


**dispaly global variables**::
	
	env

**trap**
	https://bash.cyberciti.biz/guide/Trap_statement

