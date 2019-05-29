


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






