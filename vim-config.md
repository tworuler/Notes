# Vim插件

## Vundle

[Vundle](https://github.com/VundleVim/Vundle.vim)是一个vim插件管理器。

### Vundle安装

```bash
git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim
```

### Vundle配置

将下面代码加入到`.vimrc`中

```vim
set nocompatible
filetype off
set rtp+=~/.vim/bundle/Vundle.vim
call vundle#begin()

Plugin 'VundleVim/Vundle.vim'

call vundle#end()
filetype plugin on
```

### Vundle使用

 * 在`call vundle#begin()`和`call vundle#end()`之间添加要安装的插件
 * 启动vim并运行命令`:PlugingInstall`
 * 终端安装插件命令: `vim +PluginInstall +qall`

## YouCompleteMe

[YouCompleteMe](https://github.com/Valloric/YouCompleteMe)是一个非常优秀的代码补全插件，但安装过程较复杂，需要vim版本较高，目前未使用。

## NERDTree

[NERDTree](https://github.com/scrooloose/nerdtree)树形目录插件，能用来浏览文件系统，打开文件。

### NERDTree安装

使用Vundle安装

```vim
Plugin 'scrooloose/nerdtree'
```

### NERDTree配置

```vim
" F2打开或关闭NERDTree
nnoremap <silent> <f2> :NERDTreeToggle<CR>
" 需要忽略的文件
let NERDTreeIgnore=['\.o']
" 只有NERDTree一个窗口还开着的时候，退出vim
autocmd bufenter * if (winnr("$") == 1 && exists("b:NERDTree") && b:NERDTree.isTabTree()) | q | endif
" NERDTree显示行号
let NERDTreeShowLineNumbers=1
```

### NERDTree使用

常用快捷键

```
?:  打开NERDTree帮助
o:  在已有窗口中打开文件，并跳到该窗口
go: 在已有窗口中打开文件，但不跳到该窗口
t:  在新Tab中打开文件，并跳到新Tab
T:  在新Tab中打中文件，但不跳到新Tab
i:  split一个新窗口打开文件，并跳到该窗口
gi: split一个新窗口打开文件，但不跳到该窗口
s:  vsplit一个新窗口打开文件，并跳到该窗口
gs: vsplit一个新窗口打开文件，但不跳到该窗口
A:  最大化NERDTree窗口或恢复大小
```
