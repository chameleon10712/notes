==========
參考 Link
==========

- `git handbook <https://shainer.gitbooks.io/git-handbook/content/some_basic_definitions.html>`_
- `開始 Git 基礎要點 <https://git-scm.com/book/zh-tw/v1/開始-Git-基礎要點>`_
- `About Version Control <https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control>`_
- `檔案還原 <https://zlargon.gitbooks.io/git-tutorial/content/file/recover.html>`_

|

=============
    local
=============

Initialization(初始化 把當前目錄變成git 的repository) ::
	
	$git init


Working Directory ::
	
	$git add new-file


Staging Area(準備進歷史紀錄; 暫存區) ::

	$git commit
	...


Database(history) ::
	
	$git log


==============
    remote
==============
Push(把local 端的東西同步到遠端) ::

	#          <remote>  <branch 名字>
	$git push   origin     master


Pull(把遠端的東西拉過來) ::
	
	$git pull


Remote ::
	
	# 把remote 列表顯示出來
	$git remote
	
	# 把remote 列表詳細顯示
	$git remote -v

	# 新增一個remote 叫作origin
	$git remote add origin <URL>


==========================
    放東西到github上 
==========================
1. 在github 上建repository

2. 在local 端 cd 進target 目錄 ex. cd <directory name>

4. $ git remote add origin <URL> (新增一個remote)

5. $ git remote -v (# 把remote 列表詳細顯示) 

6. $ git log (列出歷史紀錄)

7. $ git add . (把當前目錄加進staging area)(不建議)
   $ git add -A (把當前目錄下的所有檔案加進stagin area)

8. $ git status (檢查加入staging area 的檔案列表)

9. $ git reset {filename} (取消追蹤, 從staging area 中拿掉)

=======================
    修改檔案後上傳
=======================
1. $ git add -A

2. $ git status (檢查加入staging area 的檔案列表)

3. $ git reset {filename} (取消追蹤, 從staging area 中拿掉)

4. $ git commit

5. $ git push origin master



`fatal: refusing to merge unrelated histories <https://github.com/doggy8088/Learn-Git-in-30-days/issues/31>`_










