# Vim插件

## Vundle

[Vundle](https://github.com/VundleVim/Vundle.vim)是一个vim插件管理器。（如果没有特别说明，下文中插件都使用Vundle安装。）

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
nnoremap <silent> <F2> :NERDTreeToggle<CR>
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

## MiniBufExpl

[MiniBufExpl](https://github.com/fholgado/minibufexpl.vim) buffer管理工具，能显示每个buffer对应是第几个buffer。

### MiniBufExpl安装

```vim
Plugin 'fholgado/minibufexpl.vim'
```

### MiniBufExpl配置

```vim
" 使minibuffer显示在窗口最上方
let g:miniBufExplBRSplit = 0
```

### MiniBufExpl使用

没有MiniBufExpl，下面vim命令也能使用，但不知道buffer对应的num，很难用`b<num>`来切换buffer

```vim
:bn 打开后一个buffer
:bp 打开前一个buffer
:b<num> 打开第num个buffer
```

## Tagbar

[Tagbar](https://github.com/majutsushi/tagbar)能显示当前文件的tags，方便查看代码结构，如类，函数，全局变量等。

### Tagbar安装

```vim
Plugin 'majutsushi/tagbar'
```

### Tagbar配置

```vim
" F3 打开或关闭tagbar
nnoremap <silent> <F3> :TagbarToggle<CR>
```

## Taglist

[Taglist](https://github.com/vim-scripts/taglist.vim) 类似于tagbar的插件，基本能被tagbar取代，尝试后未使用。

### Taglist安装

```vim
Plugin 'taglist.vim'
```

### Taglist配置

```vim
" F3打开或关闭taglist
nnoremap <silent> <F3> :TlistToggle<CR>
" 只展示一个文件的taglist
let Tlist_Show_One_File=1
" 当taglist是最后以个窗口时自动退出
let Tlist_Exit_OnlyWindow=1
" 在右边显示taglist窗口
let Tlist_Use_Right_Window=1
" tag按名字排序
let Tlist_Sort_Type='name'
```

## indentLine

[indentLine](https://github.com/Yggdroot/indentLine)显示代码缩进。

注意：indentLine默认会改变"concealcursor" 和 "conceallevel"，会一些符号隐藏掉，如json里面的引号，和markdown里面的一些符号。目前json和markdown里面的符号隐藏问题由下文其他插件解决。

### indentLine安装

```vim
Plugin 'Yggdroot/indentLine'
```

### indentLine配置

```vim
" Vim 设置显示符号颜色
let g:indentLine_color_term = 239
" GVim 设置显示符号颜色
let g:indentLine_color_gui = '#A4E57E'
" 设置显示符号， ¦, ┆, 或 │
let g:indentLine_char = '¦'
" 默认关闭indentLine
let g:indentLine_enabled = 0
```

## Indent Guides

[Indent Guides](https://github.com/nathanaelkane/vim-indent-guides) 显示代码缩进的另一个插件。未使用，indentLine更好看。

### Indent Guides安装

```vim
Plugin 'nathanaelkane/vim-indent-guides'
```

### Indent Guides配置

```vim
" 默认打开状态
let g:indent_guides_enable_on_vim_startup=1
" 从第二层开始可视化显示缩进
let g:indent_guides_start_level=2
" 设置色块宽度
let g:indent_guides_guide_size=1
```
