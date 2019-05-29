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







