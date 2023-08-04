Plugin Install
==============

.. code:: sh

  sudo apt-get install git curl
  git clone https://github.com/gmarik/vundle.git ~/.vim/bundle/vundle




``~/.vimrc``

.. code-block:: sh

  filetype off
  set rtp+=~/.vim/bundle/vundle/
  call vundle#rc()

  Bundle 'tomtom/tcomment_vim'
  filetype indent plugin on



Reference

- `Vundle：Vim Plugin 自動下載、安裝、更新與管理工具（Vim Bundle） <https://blog.gtwang.org/linux/vundle-vim-bundle-plugin-manager/>`_
