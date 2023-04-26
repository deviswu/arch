# nvim-tree
nvim-tree 可以执行常见的 创建 、删除、拷贝、剪切 文件等操作
- o 打开关闭文件夹
- a 创建文件
- r 重命名
- x 剪切
- c 拷贝
- p 粘贴
- d 删除
- alt+a 
## 安装
vim-plug
```vimscript
Plug 'nvim-tree/nvim-web-devicons' " optional
Plug 'nvim-tree/nvim-tree.lua'
```
In ~/.config/nvim/init.vim:
```
call plug#begin(has('nvim') ? stdpath('data') . '/plugged' : '~/.vim/plugged')
Plug 'nvim-tree/nvim-tree.lua'
call plug#end()

lua << EOF
vim.g.loaded_netrw = 1
vim.g.loaded_netrwPlugin = 1
vim.opt.termguicolors = true
require("nvim-tree").setup()
EOF
```
