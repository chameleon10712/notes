Ubuntu
===========

新灌電腦時要裝的套件


- vim

- 更換 Ctrl 與 CapsLock

  - .. code:: sh

    sudo apt-get install gnome-tweak-tool
      
  - 安裝後，用圖形介面點

    - ``Tweaks`` > ``Keyboard & Mouse`` > ``Keyboard`` > ``Additional Layout Options`` > ``Caps Lock behavior``



- 新酷音

  - .. code:: sh
      
      sudo apt-get install fcitx fcitx-chewing
  
  - `Ubuntu: fcitx + chewing 新酷音輸入法 <https://gist.github.com/tanyuan/c0d4ee15cf0c9c93da28cc1cf0ff87b3>`_



- ssh

  - .. code:: sh
  
      sudo apt-get install ssh


  - ``vim /etc/ssh/sshd_config``
    修改
    
    .. code:: sh
    
      Port 22
      PasswordAuthentication yes

    
  - 修改後重啟 service
  
    .. code:: sh
    
      /etc/init.d/ssh restart
  
  
