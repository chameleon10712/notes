


=================================
			NFS				
=================================




mount
-----


Mac mount USB::

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


常用指令::

    df
    df -h




=====================
	改sudoers
=====================

``sudo -l``  : 看 sudo 規則
``su -`` saadmin 換user

visudo 在 ``/usr/local/etc/sudoers``

sudo visudo::

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

vim /etc/ssh/sshd_config		#看哪一個user可以連這台機器::

    AllowGroups     sysadm	


service sshd restart	 	#重開daemon








======================
	更改檔案權限
======================

通常
- file	644
- dir	755


::

    d      rwx         r-x         r-x
           owner       group       other


::

        file            director
    -------------------------------------
    r:	read            ls
    w:	write           create file/dir
    x:	execute         cd


::

    chown -R sauser:nctucs sauser       #change owner
    chgrp                               #change group


