`[cheatsheet] <https://gist.github.com/MohamedAlaa/2961058>`_

tmux 設定檔 ``vim  .tmux.conf``

|

===================
	tmux 指令
===================
start new ``tmux``

start new with session name  ``tmux new -s myname``


**Windows**

Creating Windows  ``Ctrl-b`` + ``c``

Switch to previous window  ``Ctrl-b`` + ``p``

Switch to next window  ``Ctrl-b`` + ``n``

Switch to specific window  ``Ctrl-b`` + ``<number>``

Rename the current window  ``Ctrl-b`` + ``,``


**Panes**

Splitting Panes

* ``Ctrl-b`` + ``%``    #左右split

* ``Ctrl-b`` + ``"``   #上下split

Navigating Panes  ``Ctrl-b`` + ``<arrow key>``  #移動到上/下/左/右的pane

Closing Panes::

	exit
	Ctrl + d  #退出現在的pane

Make a pane go full screen::

	Ctrl-b + z  # go full screen
	Ctrl-b + z  #(again) shrink it back to its previous size

**Sessions**

一組tmux 視窗(several windows)

Detach  ``Ctrl-b`` + ``d``

Attach ``tmux attach``

attach to name  ``tmux a -t myname``


List all available commands  ``Ctrl-b`` + ``?``











