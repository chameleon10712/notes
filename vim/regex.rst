================================
    regular expression - vim	
================================

好用連結

- `link <http://club.cc.cmu.edu/talks/fall15/power-vim.html>`_


google keyword

- vim regular expression
	
- `vim regex <http://vimregex.com/>`_


**exact match**:  ``/\<exact_word\>``


**replace word**:

``:n1,n2s/word1/word2/g``

``:1,$s/word1/word2/g``

``:1,$s/word1/word2/gc``


**insert newline**:  ``\r``

**inser tab**:  ``Ctrl + V``  and then press ``<tab>``


**4 digits**:  ``\d\{4}``


**group**
	
- ``\(.*\)``
- ``\1``


**match whitespace**
	
* ``\s``  whitespace character

* ``\S``  non-whitespace character

**match blank lines**
	
``^\s*$``

- ``^`` is the beginning of string anchor
- ``$`` is the end of string anchor
- ``\s`` is the whitespace character class
- ``*`` is zero-or-more repetition of


**convert the ^M linebreak to 'normal' linebreak in a file opened in vim**

``:%s/<Ctrl-V><Ctrl-M>/\r/g``

Where <Ctrl-V><Ctrl-M> means type Ctrl+V then Ctrl+M


**non-greedy match**  ``.\{-}``

Instead of ``.*`` use ``.\{-}``
``:help non-greedy``


`match non greedy in vim <http://stackoverflow.com/questions/1305853/how-can-i-make-my-match-non-greedy-in-vim>`_


