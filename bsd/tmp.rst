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
:

    /etc/passwd
    /etc/master.passwd





