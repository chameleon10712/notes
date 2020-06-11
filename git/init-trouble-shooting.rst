Init Repo
============

當你在 GitHub 建了一個 Repo, 在 local 端

.. code::
  
  $ git init
  
  $ git remote add origin <URL>
  
  $ git remote -v


在 commit 新檔的時候會出現 error 

.. code::

  To https://github.com/your_github/example.git
   ! [rejected]        master -> master (fetch first)
  error: failed to push some refs to 'https://github.com/your_github/example.git'
  hint: Updates were rejected because the remote contains work that you do
  hint: not have locally. This is usually caused by another repository pushing
  hint: to the same ref. You may want to first integrate the remote changes
  hint: (e.g., 'git pull ...') before pushing again.
  hint: See the 'Note about fast-forwards' in 'git push --help' for details.


Solution

.. code::

  $ git fetch origin master
  
  $ git merge origin/master --allow-unrelated-histories
  
  $ git rebase master



從 git 2.9.0 開始預設行為不允許合併沒有共同祖先的分支。
你需要加上 ``--allow-unrelated-histories`` 選項才不會出現這個錯誤訊息。

|

Undo init

.. code::

  rm -rf .git


|

Undo git add

.. code::

  git reset <file>



|


Reference
------------

- `blog <https://cythilya.github.io/2018/06/19/git-merge-branch-into-master/>`_
- `github 討論 <https://github.com/doggy8088/Learn-Git-in-30-days/issues/31>`_
- `stackoverflow - undo git init <https://stackoverflow.com/questions/3212459/is-there-a-command-to-undo-git-init>`_
- `stackoverflow - undo git add <https://stackoverflow.com/questions/348170/how-do-i-undo-git-add-before-commit>`_

