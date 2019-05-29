


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
::

    sudo /etc/netstart
    sudo service ypbind restart


ypwhich
-------

return hostname of YP server of map master




把 passwd 從原本的 /etc/ 改到 /var/yp
-----------------------------------


::

    touch master.passwd
    (vipw passwd ?)
    vipw -d /var/yp 

    ypinit -m +sa.nis


    vipw  vi -> vim :

    vim ~/.bashrc:  export EDITOR=vim (一般使用者&root都要設)
    vim ~/.cshrc:	setenv EDITOR vim





add user
--------

::

    sudo pw useradd newuser -V /var/yp -b /net/home -m -h 0 -Y -u uid -g group
    make
    ypinit -m +sa.nis



delete user
-----------
::

    vipw master.passwd
    make






