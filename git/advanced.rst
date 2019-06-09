Advanced
========


Sync your Git Fork to the Original Repo
---------------------------------------

`[Blog] <https://digitaldrummerj.me/git-syncing-fork-with-original-repo/>`_



Stash
-----

`[git book 中文] <https://git-scm.com/book/zh-tw/v1/Git-%E5%B7%A5%E5%85%B7-%E5%84%B2%E8%97%8F-Stashing>`_


Replace File in Merge Conflict
------------------------------

In a git merge, how do you just replace your version with the version git says there is a conflict with?

.. code-block:: sh

  git pull                             # fetch/merge partners changes
  # merge fails, conflict
  git checkout origin FILE_TO_REPLACE  # replace changes with partners ver
  git commit                           # finish merge



`[ref] <https://stackoverflow.com/questions/3515657/in-a-git-merge-how-do-you-just-replace-your-version-with-the-version-git-says-t>`_


Abort Merge
-----------

`[StackOverflow] <https://stackoverflow.com/questions/11646107/you-have-not-concluded-your-merge-merge-head-exists>`_

