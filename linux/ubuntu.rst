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


GitLab
=========

下面設定是 global git aacount setting, 如果要 local 的要改


Configure Git

.. code:: sh

  git config --global user.name "your_username"
  git config --global user.email "your_email_address@example.com"
  git config --global --list




Git authentication methods


- RSA SSH keys

  .. code:: sh

    ssh-keygen -t rsa -b 2048 -C "email@example.com"


  執行後會產生

  .. code:: sh

    Enter file in which to save the key (/home/user/.ssh/id_ed25519):


  輸入 ``gitlab`` 後，會產生 ``gitlab_rsa``, ``gitlab_rsa.pub``


  .. code:: sh

    cat gitlab_rsa.pub


  複製輸出的文字後，到 gitlab 右上角個人圖像 > setting > SSH Keys , 將剛剛那段文字貼到 Key 大框, title 打你的電腦名稱, 點 Add key

|



Reference

- `Start using Git on the command line <https://docs.gitlab.com/ee/gitlab-basics/start-using-git.html>`_


