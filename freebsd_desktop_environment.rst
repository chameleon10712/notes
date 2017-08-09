=====================================

	FreeBSD Desktop Environment

=====================================

1. pkg install xorg
2. pkg install gnome3



start Xorg ::
	
	startx
exit Xorg or others(?) ::
	
	ctrl + alt + F1

check graphic card version 顯示PC 硬體版本詳細資訊，可以用這個查顯卡版本::
	
	pciconf -lv


Lab PC

nvidia gtx 750




==================
  nVidia driver
==================

1.  svnlite : FreeBSD source code 需要由 svnlite 去抓 (現在用git 抓好像也可以？
	releng  : release branch 後續維護版本

	nvidia-driver-346.96 requires kernel source files in /usr/src ::
	svnlite checkout svn://svn.tw.freebsd.org/base/releng/11.0/ /usr/src

2.  kldload 動態載入 linux, linux64
    kldload -- load a file into the kernel ::
	
	kldload linux
	kldload linux64

3. ::
	cd /usr/ports/x11/nvidia-driver
	make install clean
	
4. /boot/loader.conf ::
	
	nvidia_load="YES"

5. ::
	cd /usr/ports/x11/nvidia-setting
	make install clean

6. ::
	cd /usr/ports/x11/nvidia-xconfig
	make install clean






