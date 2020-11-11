Ubuntu
===========

新灌電腦時要裝的套件


- vim

- 更換 Ctrl 與 CapsLock

  - .. code:: sh

      sudo apt-get install gnome-tweak-tool
      
  - 安裝後，用圖形介面點

    - ``Tweaks`` > ``Keyboard & Mouse`` > ``Keyboard`` > ``Additional Layout Options`` > ``Caps Lock behavior``


- Install git

  - .. code:: sh

      sudo apt-get install git


- 新酷音

  - .. code:: sh
      
      sudo apt-get install fcitx fcitx-chewing
  
  - `Ubuntu: fcitx + chewing 新酷音輸入法 <https://gist.github.com/tanyuan/c0d4ee15cf0c9c93da28cc1cf0ff87b3>`_



- ping 工具

  - .. code:: sh
  
      sudo apt-get update
      sudo apt-get install iputils-ping


- pip

  - .. code:: sh

      sudo apt-get install python-pip


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
  
  
- 安裝 Chromium

  - .. code:: sh
  
      sudo apt-get install chromium-browser
  


- 安裝 Gedit

  - .. code:: sh
  
      sudo apt-get install gedit



- 安裝 Steam

  - .. code:: sh
  
      sudo apt-get install steam

|



