GitLab
=========

下面設定是 global git account setting, 如果要 local 的要改


Configure Git

.. code:: sh

  git config --global user.name "your_username"
  git config --global user.email "your_email_address@example.com"
  git config --global --list




Git authentication methods


- RSA SSH keys

  .. code:: sh

    ssh-keygen -t rsa -b 2048 -C "<comment>"


  執行後會產生

  .. code:: sh

    Enter file in which to save the key (/home/user/.ssh/id_ed25519):


  輸入 ``gitlab_rsa`` 後，會產生 ``gitlab_rsa``, ``gitlab_rsa.pub``


  .. code:: sh

    cat gitlab_rsa.pub


  複製輸出的文字後，到 gitlab 右上角個人圖像 > setting > SSH Keys , 將剛剛那段文字貼到 Key 大框, title 打你的電腦名稱, 點 Add key

|

- ~/.ssh/config

  .. code:: sh

  Host gitlab.com
  Hostname gitlab.com
  User git
  IdentityFile ~/.ssh/gitlab_rsa


|

- ssh key 設定完成後, 測試

  .. code:: sh
  
    ssh -T git@gitlab.com

  會看到
  
  .. code:: sh
  
    Welcome to GitLab, @<your_username>!
  

Reference

- `Start using Git on the command line <https://docs.gitlab.com/ee/gitlab-basics/start-using-git.html>`_

- `SSH Clone Permission denied (publickey) - All Users & All Repositories <https://gitlab.com/gitlab-org/gitlab-foss/-/issues/26022>`_

