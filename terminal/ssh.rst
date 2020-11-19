=============
設定 ssh host
=============

http://carlleesnote.blogspot.tw/2015/07/sshlinuxmac.html

cd ~/.ssh

vim config

=============
  ssh key
=============

Client

::
	
	cd ~/.ssh
	ssh-keygen


- id_rsa      ->  client
- id_rsa.pub  ->  server



Server

1. Copy public key to Server: ``~/.ssh/authorized_keys``


2. Change sshd config: ``/etc/ssh/sshd_config``


::

	PasswordAuthentication no
	PubkeyAuthentication yes



3. restart sshd service: ``/etc/init.d/sshd restart``
