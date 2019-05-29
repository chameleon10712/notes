=============
Virtual Host
=============

qualified domain name

	- https://wiki.apache.org/httpd/CouldNotDetermineServerName

virtual host setting : httpd.conf
http://httpd.apache.org/docs/current/vhosts/name-based.html



=========
 version
=========

curl -v chameleon.idv.tw

apache24/httpd.conf::
	
	ServerSignature off
	ServerTokens prod


+ hide php version
/usr/local/etc/php.ini::
	
	expose_php = Off

===================
	DNS		
===================

Forward Domain (正解) : domain name -> IP  (Forward mapping)
Reverse Domain (反解) : IP -> domain name  (Reverse mapping)

+ Name Server 

    - master (Primary)   server
    - slave  (Secondary) server

    - cach only server 

    - Forwarder  

        - DNS主機遇到非本機負責zone之查詢請求的時候，將不直接向root zone查詢而把請求轉交給指定的forwarder(一台或多台)主機代為查詢


+ DNS Queries 詢問

    - Recursive Queries
    - Iterative Queries
    - Inverse Queries


