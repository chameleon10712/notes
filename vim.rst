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


============================
	regular expression
============================
google keyword:
	vim regular expression
	`link <http://vimregex.com/>`_

exact match::

	/\<exact_word\>


replace word::

	:n1,n2s/word1/word2/g
	
	:1,$s/word1/word2/g
	
	:1,$s/word1/word2/gc

insert newline::
	
	\r

inser tab::
	
	Ctrl + V 
	and then press tab

4 digits::
	
	\d\{4}

group::
	
	\(.*\)
	\1	

match whitespace::
	
	\s
	whitespace character
	
	\S
	non-whitespace character

match blank lines::
	
	^\s*$


	^ is the beginning of string anchor
	$ is the end of string anchor
	\s is the whitespace character class
	* is zero-or-more repetition of

convert the ^M linebreak to 'normal' linebreak in a file opened in vim::

	:%s/<Ctrl-V><Ctrl-M>/\r/g
	
	Where <Ctrl-V><Ctrl-M> means type Ctrl+V then Ctrl+M

non-greedy match::
	
	.\{-}

	Instead of .* use .\{-}
	:help non-greedy
http://stackoverflow.com/questions/1305853/how-can-i-make-my-match-non-greedy-in-vim



============
   setting
============
find vimrc ::

	vim ~/.vimrc


Highlight current line ::
	
	:set cursorline

Highlight ::
	
	:set hls

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

http://hackerandgeek.blogspot.tw/2013/08/vim.html

mapping example::
	
	nnoremap t :s/^\s*\(\S.*\S\)\s*$/    \1    /<CR>yyP0<C-v>$hr=yyjpj









