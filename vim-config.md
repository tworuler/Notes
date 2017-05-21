# 常用插件

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
