# Customize vim
## NeoBundleの導入
### NeoBundleとは？
vimのプラグイン管理ツール。

### vundleとの違い
公式ドキュメントからの引用

コマンド名が改善されている
vital化されている
shellslashがオンでも動作する
vimprocに対応している
unite.vimインタフェースの実装
Subversion, Mercurialへの対応
リビジョン指定

### 使い方
 $ curl https://raw.githubusercontent.com/Shougo/neobundle.vim/master/bin/install.sh > install.sh
 $ sh ./install.sh
下記をvimrcに追記

"NeoBundle Scripts-----------------------------
if &compatible
  set nocompatible               " Be iMproved
endif

" Required:
set runtimepath^=/home/vagrant/.vim/bundle/neobundle.vim/

" Required:
call neobundle#begin(expand('/home/vagrant/.vim/bundle'))

" Let NeoBundle manage NeoBundle
" Required:
NeoBundleFetch 'Shougo/neobundle.vim'

" Add or remove your Bundles here:
NeoBundle 'Shougo/neosnippet.vim'
NeoBundle 'Shougo/neosnippet-snippets'
NeoBundle 'tpope/vim-fugitive'
NeoBundle 'ctrlpvim/ctrlp.vim'
NeoBundle 'flazz/vim-colorschemes'

" You can specify revision/branch/tag.
NeoBundle 'Shougo/vimshell', { 'rev' : '3787e5' }

" Required:
call neobundle#end()

" Required:
filetype plugin indent on

" If there are uninstalled bundles found on startup,
" this will conveniently prompt you to install them.
NeoBundleCheck
"End NeoBundle Scripts-------------------------
vi上から、:NeoBundleInstall で.vimrcのNeoBundleで指定されているリポジトリのプラグインをインストールできる。
プラグインを削除したい場合は、vimrc上からNeoBundleの記述を消して :NeoBundleClean でできる。
