好用連結

- `cmu cc <http://club.cc.cmu.edu/talks/fall15/power-vim.html>`_

|

============
	Vim
============




inset '#' at the beginning visualized text::
	
	<C-v> I # <esc> 


=====================
	normal mode
=====================

游標移到檔案最上方::	
	
	gg

把這次highlight 的東西塗掉::
	
	:noh

repeat last command :  use ``.``


Fix indentation : ``gg=G``

- gg : 移到檔案最上方
- = : 排版
- G : 到整個檔案的最下方


============
   setting
============
find vimrc   ``vim ~/.vimrc``

Highlight current line  ``:set cursorline``

Highlight  ``:set hls``

==================
	vim macro	
==================

1.紀錄::
	
	先在最外層 按下 "q" , 再按下你想要的巨集名稱, 例如: a

2.輸入想要編輯的步驟::

	此時左下方會顯示 "recording" , 代表已經在紀錄中, 此時你所有
	輸入的編輯指令都會被紀錄在巨集 a 當中. 例如: 我 i + teststring + Esc
	
3.離開紀錄模式::
	
	Esc -> q

4.播放巨集::
	
	按下 @a, 播放剛才紀錄的巨集, 這樣就會播放一次

5.連續播放巨集::
	
	按下 10@a, 就會播放剛才紀錄的巨集 10 次

- `link <http://hackerandgeek.blogspot.tw/2013/08/vim.html>`_


mapping example::
	
	nnoremap t :s/^\s*\(\S.*\S\)\s*$/    \1    /<CR>yyP0<C-v>$hr=yyjpj









