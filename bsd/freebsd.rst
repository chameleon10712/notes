============================
     pkg installed list
============================
FreeBSD 10.x ::
	
	pkg info


=========================
	製作開機USB
=========================

diskutil list
sudo diskutil unmount /dev/disk2s1
sudo dd if=FreeBSD-10.3-RELEASE-amd64-memstick.img.xz of=/dev/rdisk2 bs=1m conv=sync


------ Install without Network ------ 

-memstick.img: 
This file contains all of the files needed to install FreeBSD, its source, and the Ports Collection. It should be burned to a USB stick using the instructions below.


===============================
	disable secure boot
===============================
解決主機板綁定 windows 作業系統問題

http://www.technorms.com/45538/disable-enable-secure-boot-asus-motherboard-uefi-bios-utility


============
    vipw
============
/etc/passwd
/etc/master.passwd


When run without options, vipw will work with the password files in /etc.
Once the information has been verified, vipw uses pwd_mkdb(8) to update the user database.

The passwd file is generated from the master.passwd file by pwd_mkdb(8)











=================
	關機指令
=================

freeBSD  關機指令 shutdown -p now
Linux    關機指令 shutdown -P now


==================
	version
==================

FreeBSD-A.B.C-Type

A: major version Number	(大幅度改變
B: minor version Number	(小幅度改變
C: slight patch version number	(修 bug

=============
	MBR
=============

MBR : Master Boot Record (開機的時候選OS的地方


SATA

# : root
$ : 一般使用者



使用者 install 的東西會放在 (習慣上
/user/local/bin	-> freeBSD  
/user/bin		-> Linux

FreeBSD 8 以前只有port ~

FreeBSD 內建的 shell : Bourne Shell, Csh, Tcsh




9/29

一定要裝 ca_root_nss

pkg ng(?

第一次執行的 pkg 會要你裝 pkg
第一次執行的 pkg 在 -> /user/sbin/pkg (BSD bundle 的

where pkg
-> /usr/sbin/pkg.
-> /usr/local/sbin/pkg



awk
sed(?


HW2

3-1  Filesystem Statistic (20%) 檔案系統統計
3-2  Dialog Browser (60%)

HW3



/etc/auto_master
autos -> kld ? kldload ?








=================================================

		HW3 Part 1 : ZFS backup
=================================================
spec:

./zbackup [[--list | --delete] target dataset [ID] | target dataset [rotation count]]




可以用的 command line tool / utility : 
	drive
	https://github.com/odeke-em/drive


ZFS
http://mutolisp.logdown.com/posts/247630-zfs-file-system-notes


=======================
	shell script 
=======================

sudo	 sh	 test.sh		aa		bbb		PPAP
			$0		$1		$2		$3

$@ : aa bbb PPAP
$# : 3


=========================
	create z pool
=========================


	pool		dataset(zfs)
	disk		file system


dd if=/dev/zero of=filename(your pool name) bs=1M count=10

Ex. 
dd if=/dev/zero of=backup_pool bs=64M count=10




==========
   zfs
==========

zfs create backup_pool/data2

zfs snapshot backup_pool/data2@tmp1

ls /backup_pool/data/.zfs/snapshot    

zfs destroy backup_pool/data@tmp1

zfs list -t snapshot


—— compression ——

zfs set compression=gzip backup_pool/data

zfs get compression


*** 不能再虛擬硬碟做(?) ***
zfs send backup_pool/data@2016-11-21-01:15:00 > data@2016-11-21-01:15:00
xz data@2016-11-21-01:15:00


zfs send pool/fs@snap | gzip > backupfile.gz

find /backup_pool/*/.zfs/snapshot/* -type d


====================
	顯示當前時間
====================

date ‘+%Y/%m/%d %H:%M:%S'

date '+%+'

date

stat -f "%Sm" -t "%Y-%m-%d %H:%M" /backup_pool/Snapshots/tmp1

======================
	NTP 時間校正
======================
校時

ntpdate -b pool.ntp.org

======================
	  好用參數
======================
!! : 上一個指令

ntpdate -b pool.ntp.org
sudo !!


!$ : 上一個指令的最後一個參數

mkdir complicated-folder-name
cd !$


ls -1 : 一個file/dir一行

數當前目錄有多少個files & directory:
	ls -1 | wc -l

ls -t1 /backup_pool/data : 以時間 sort file ，由早到晚 

ls -tr1 /backup_pool/data : 以時間 sort file ，由晚到早 

================
	xargs
================

find . -type f | xargs -I{} echo test{}test





====================================================

	Github project “ drive “ for Google Drive
====================================================
sudo drive init

上傳檔案到 Google Drive
sudo drive push -destination Snapshots /backup_pool/data/nice_file

下載檔案到 local machine
sudo drive pull -files Snapshots/tmp1





====================
tar cvfP tmp.tar /backup_pool/data/.zfs/snapshot







========================================

		NFS 作業 (+ NIS )  spec

========================================






=========================
		NIS
=========================

The databases used to store the information are called NIS maps
these maps are stored in stored in /var/yp/[domainname]


initialize the NIS maps::
	ypinit -m sa-domain


/etc/netstart  
(restart the network and apply the values defined in /etc/rc.conf)

chgrp : change group for files or directories

saduty -> ypcat passwd


=====================
	NIS Client	
=====================

vim /etc/rc.conf::
	nisdomainname="test-domain"
	nis_client_enable="YES"


vim /etc/master.passwd::
	+:::::::::
sudo vipw


vim /etc/group::
	+:*::

— restart —
sudo /etc/netstart
sudo service ypbind restart




===========
  ypwhich  
===========
return hostname of YP server of map master


============================================
	把 passwd 從原本的 /etc/ 改到 /var/yp
============================================
touch master.passwd
(vipw passwd ?)
vipw -d /var/yp 

ypinit -m +sa.nis


vipw  vi -> vim :

vim ~/.bashrc:  export EDITOR=vim (一般使用者&root都要設)
vim ~/.cshrc:	setenv EDITOR vim

==========
 add user
==========
sudo pw useradd newuser -V /var/yp -b /net/home -m -h 0 -Y -u uid -g group
make
ypinit -m +sa.nis

=============
 delete user
=============
vipw master.passwd
make






=================================
			NFS				
=================================




===============
	mount 
===============

Mac mount USB

/dev/disk1s1 on /Volumes Transcend

[ client ]	mount	[ server ]
/net/home				/net/home
(mount point)



/etc/fstab
/etc/exports


server : showmount -a  
//查詢 NFS Server 分享什麼資源
//-a List all mount points in the  form:host:dirpath. 
# 誰連我的資料夾


client : showmount -e sahome 
# 列出有哪些資料夾是從sahome mount 起來的


ps ax | grep mountd //確認 mountd 是否執行


[Server]

service nfsd start —> mounts also starts automatically
service nfsd status
 


常用指令：
df
df -h



=====================
	改sudoers
=====================

sudo -l  : 看 sudo 規則
su - saadmin 換user

visudo 在 /usr/local/etc/sudoers

sudo visudo 
	#include /net/admin/sudoers

/net/admin/sudoers::	

	Cmnd_Alias    SU = /usr/bin/su
	Cmnd_Alias    REBOOT = /sbin/halt, /sbin/reboot,\
					   /sbin/poweroff
	Cmnd_Alias    SHELLS = /bin/*sh
	%sysadm ALL = ALL, !SU, !SHELLS, !REBOOT


====================
	限制連線
====================

vim /etc/hosts.allow		#看哪一個host 可以連這台機器

vim /etc/ssh/sshd_config		#看哪一個user可以連這台機器
	AllowGroups     sysadm	

service sshd restart	 	#重開daemon


======================
	更改檔案權限
======================
通常
file	644
dir	755


d	rwx		r-x		r-x
	owner		group		other
			
	file		   director
-------------------------------------
r:	read			ls
w:	write			create file/dir
x:	execute		cd



chown -R sauser:nctucs sauser		#change owner
chgrp						#change group







===================================================

		Managing Services in FreeBSD

===================================================




====================
	usage 表示法	
====================

Usage: /etc/rc.d/bgfsck [fast|force|one|quiet](start|stop|restart|rcvar|enabled|describe|extracommands)

[] : optional
() : 一定要加的參數，()內選一個


========================
	service onestart	
========================

如果 /etc/rc.conf 沒有 enable sshd，但是想要用sshd servce  => onestart

service sshd onestart
service sshd onerestart


====================
	/etc/rc.d		
====================

provide basic services which can be controlled with the start, stop, and restart options to service(8)


===============
	rc(8)	
===============

command scripts for auto-reboot and daemon startup


--- rc.conf ---

	 system configuration information

	The file rc.conf contains descriptive information about the local host
     name, configuration details for any potential network interfaces and
     which services should be started up at system initial boot time.


--- rc.d ---
	
	The rc.d/ directories contain scripts which will be automatically executed
	at boot time and shutdown time.



==============================
	service sshd rcvar
==============================

To check if a service is enabled in /etc/rc.conf

rcvar        Display which rc.conf(5) variables are used to control
             the startup of the service (if any).


==================
	sh(1)
==================

:       A null command that returns a 0 (true) exit value.

. file  The commands in the specified file are read and executed by the
             shell.  The return command may be used to return to the .
             command's caller.  If file contains any '/' characters, it is
             used as is.  Otherwise, the shell searches the PATH for the file.
             If it is not found in the PATH, it is sought in the current
             working directory.




============================================================

			Write a daemon in FreeBSD

============================================================


https://www.freebsd.org/doc/en/articles/rc-scripting/rcng-daemon-adv.html


=======================
	RC srcipt
=======================

reload signal : 預設是 SIGHUP ，但可以用 sig_reload 修改
stop signal : 預設是 SIGTERM ，但可以用 sig_stop 修改

ex. ( in rc script ) 

sig_reload="USR1"


command="/usr/sbin/${name}"
這個rc 要執行的檔案

command_interpreter :  

	You should additionally set command_interpreter to let rc.subr(8) know the
	actual name of the process if $command is a script.


${name}_program 執行順序優先於 command




================
	SIGHUP	
================

等同於 kill -1





sudo daemon -p /var/run/zbackup.pid ./zbackup.sh backup_pool/data2 5









=================================================
		常見問題(single user mode)
=================================================

=> fsck: exec fsck_nullfs for sahome:/vol/home in /sbin:/usr/sbin: No such file or directory


關鍵字： freebsd single user mode read only

解決 read only 的問題： mount -a /

http://mybsdnote.blogspot.tw/2005/12/single-user-mode.html



sahome 無法 ssh chameleon@sahome 進去
=> /etc/ssh/sshd_config
	把 AllowGroups 註解掉後就可以登了
	service sshd restart





===========================

		TODO

===========================
欠：


1.
google drive download 後rollback

2.
FreeBSD 更新問題:
如果之前版本都是用pkg install 的話，之前用pkg install的3rd軟體也要重裝嗎
Guide 上只寫要重編用port 裝的3rd software
=> 不用

3.
/usr/local/etc/rc.d/ 與 /etc/rc.d 的差異

/etc : 整個系統的設定檔
/usr/local : user 自己裝的東西 

======================
	from  hw4
======================
4. libc manual job control

https://www.gnu.org/software/libc/manual/html_node/Job-Control.html


5. htop


6. pw: user 'messagebus' disappeared during update 
不知道為什麼這樣解就對了 = =|||

vim 不知道為什麼不見了
所以 pkg install vim
install 的時候有 error message : 
pw: user 'messagebus' disappeared during update

sol : 
	sudo vipw
	:wq


參考網站
http://freebsdexperience.blogspot.tw/2014/04/pw-user-messagebus-disappeared-during.html






——Question list——

crontab
     -e      Edit the current crontab using the editor specified by the VISUAL
             or EDITOR environment variables.  The specified editor must edit
             the file in place; any editor that unlinks the file and recreates
             it cannot be used.  After you exit from the editor, the modified
             crontab will be installed automatically.


https://forums.freebsd.org/threads/58337/
http://mutolisp.logdown.com/posts/247630-zfs-file-system-notes


========================
	SA 課堂 notes
========================

console 線
115200

saltstack
BOOK
continue delivery


12/22 notes

man pf.conf
FIB forwarding interfacing base




======================
	pkg 套件升級
======================

sudo pkg upgrade python35





===============
	vim
===============

repeat last command :
	use "."


================
	Python
================

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



>>> m = re.match(r"(\w+)=(\w+)","enabled=no")
>>> m.group(0)
'enabled=no'
>>> m.group(1)
'enabled'
>>> m.group(2)
'no'
>>> m.groups()
('enabled', 'no')
>>> len(m.groups())
2


>>> m = re.match(r"(\w+)=(\w+)x(\w+)(\w+)","policy=4x15m")
>>> m.group(0)
'policy=4x15m'
>>> m.group(1)
'policy'
>>> m.group(2)
'4'
>>> m.group(3)
'15'
>>> m.group(4)
'm'


>>> m = re.match(r"(\d+)x(\d+)(\w+)","5x1d")
>>> m.group(0)
'5x1d'
>>> m.group(1)
'5'
>>> m.group(2)
'1'
>>> m.group(3)
'd'

=====================
	time stamp
=====================

>>> import time
>>> time.time()
1482580337.6782422
>>> time.time()
1482580340.361458

=================
	lambda	
=================

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


========================
	string format		
========================

>>> '{}/{}'.format('backup_pool',name)
'backup_pool/data'


======================
	subprocess
======================
Python 3.5 以上支援


>>> import subprocess
>>> subprocess.run('ls')
<filename>.tar	daemon		HW2		sahw2-check.sh	timer.py

>>> subprocess.run(['ls','-l'])



==========================
	測 signal hanlder
==========================
	



chameleon@:~ $ ps 
 PID TT  STAT    TIME COMMAND
 772 v0  I+   0:00.04 -bash (bash)
 897  1  Is+  0:00.52 -bash (bash)
 968  2  Ss   0:00.34 -bash (bash)
7923  2  R+   0:00.00 ps
7117  3  Ss   0:00.20 -bash (bash)
7893  3  S+   0:00.05 /usr/local/bin/python3.5 ./timer.py
chameleon@:~ $ kill -s USR1 7893



-s : signal name







10.211.55.4 -> sahome ::
	sudo vim /etc/hosts
	

用root 更改使用者密碼::
	
	passwd username

查詢硬體資訊::
	
	pciconf -lv

查詢安裝紀錄::
	
	pkg info  #FreeBSD 10.x
	
	pkg_info  #FreeBSD 舊版

例行工作排程 ( crontab )::
	
	crontab -e	#編寫需要做的工作或者將要執行的工作
	
	#/etc/crontab
	























