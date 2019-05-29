============================
     pkg installed list
============================
FreeBSD 10.x ::

    pkg info


=========================
	製作開機USB
=========================

::

    diskutil list
    sudo diskutil unmount /dev/disk2s1
    sudo dd if=FreeBSD-10.3-RELEASE-amd64-memstick.img.xz of=/dev/rdisk2 bs=1m conv=sync


Install without Network
-----------------------

- memstick.img:

  - This file contains all of the files needed to install FreeBSD, its source, and the Ports Collection. It should be burned to a USB stick using the instructions below.



===============================
	disable secure boot
===============================
解決主機板綁定 windows 作業系統問題

`[link] <http://www.technorms.com/45538/disable-enable-secure-boot-asus-motherboard-uefi-bios-utility>`_




============
    vipw
============
::

  /etc/passwd
  /etc/master.passwd


When run without options, vipw will work with the password files in /etc.
Once the information has been verified, vipw uses pwd_mkdb(8) to update the user database.

The passwd file is generated from the master.passwd file by pwd_mkdb(8)




=================
	關機指令
=================

- freeBSD  關機指令 ``shutdown -p now``
- Linux    關機指令 ``shutdown -P now``





==================
	version
==================

FreeBSD-A.B.C-Type

::

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
- ``/user/local/bin``	-> freeBSD  
- ``/user/bin``		-> Linux

FreeBSD 8 以前只有port ~

FreeBSD 內建的 shell : Bourne Shell, Csh, Tcsh





2016/9/29

- 一定要裝 ca_root_nss

pkg ng(?

- 第一次執行的 pkg 會要你裝 pkg
- 第一次執行的 pkg 在 -> /user/sbin/pkg (BSD bundle 的


where pkg

- ``/usr/sbin/pkg``
- ``/usr/local/sbin/pkg``



- awk
- sed




HW2

- 3-1  Filesystem Statistic (20%) 檔案系統統計
- 3-2  Dialog Browser (60%)

HW3


- ``/etc/auto_master``
- autos -> kld ? kldload ?



=================================================
		HW3 Part 1 : ZFS backup
=================================================
spec:

``./zbackup [[--list | --delete] target dataset [ID] | target dataset [rotation count]]``




可以用的 command line tool / utility :

drive

`[link] <https://github.com/odeke-em/drive>`_


ZFS

`[link] <http://mutolisp.logdown.com/posts/247630-zfs-file-system-notes>`_






=======================
	shell script 
=======================
::

    sudo    sh  test.sh      aa     bbb      PPAP
                $0           $1     $2       $3


- $@ : aa bbb PPAP
- $# : 3




=========================
	create z pool
=========================

::

	pool		dataset(zfs)
	disk		file system


``dd if=/dev/zero of=filename(your pool name) bs=1M count=10``


Ex. ``dd if=/dev/zero of=backup_pool bs=64M count=10``





==========
   zfs
==========
::

    zfs create backup_pool/data2

    zfs snapshot backup_pool/data2@tmp1

    ls /backup_pool/data/.zfs/snapshot    

    zfs destroy backup_pool/data@tmp1

    zfs list -t snapshot



compression
-----------

::

    zfs set compression=gzip backup_pool/data
    zfs get compression




*** 不能在虛擬硬碟做(?) ***
::
    zfs send backup_pool/data@2016-11-21-01:15:00 > data@2016-11-21-01:15:00
    xz data@2016-11-21-01:15:00
    

    zfs send pool/fs@snap | gzip > backupfile.gz

    find /backup_pool/*/.zfs/snapshot/* -type d






====================
	顯示當前時間
====================
::

    date ‘+%Y/%m/%d %H:%M:%S'

    date '+%+'

    date

    stat -f "%Sm" -t "%Y-%m-%d %H:%M" /backup_pool/Snapshots/tmp1




======================
	NTP 時間校正
======================
校時

``ntpdate -b pool.ntp.org``




======================
	  好用參數
======================
``!!`` : 上一個指令

::

    ntpdate -b pool.ntp.org
    sudo !!


``!$`` : 上一個指令的最後一個參數

::

    mkdir complicated-folder-name
    cd !$


``ls -1`` : 一個file/dir一行

數當前目錄有多少個files & directory: ``ls -1 | wc -l``

``ls -t1 /backup_pool/data`` : 以時間 sort file ，由早到晚 

``ls -tr1 /backup_pool/data`` : 以時間 sort file ，由晚到早 




================
	xargs
================

``find . -type f | xargs -I{} echo test{}test``





====================================================
	Github project “ drive “ for Google Drive
====================================================
sudo drive init

上傳檔案到 Google Drive ::

    sudo drive push -destination Snapshots /backup_pool/data/nice_file

下載檔案到 local machine ::

    sudo drive pull -files Snapshots/tmp1









``tar cvfP tmp.tar /backup_pool/data/.zfs/snapshot``





========================================
		NFS 作業 (+ NIS )  spec
========================================



NIS
---

The databases used to store the information are called NIS maps
these maps are stored in stored in /var/yp/[domainname]


initialize the NIS maps::
	``ypinit -m sa-domain``


``/etc/netstart``
(restart the network and apply the values defined in /etc/rc.conf)

``chgrp`` : change group for files or directories

saduty -> ypcat passwd

