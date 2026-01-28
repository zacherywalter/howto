# neovim_setup.md

##### zsh

```shell
sudo apt install zsh
```

##### vim=nvim

in the .zshrc file

```shell
alias vim=nvim
```

i think, source ~/.zshrc reinits the .zshrc file

##### swapping caps and esc key in windows

[GitHub - susam/uncap: Map Caps Lock to Escape or any key to any key](https://github.com/susam/uncap#windows-scancode-map-registry-value)

Reg-edit Scancode Map to edit:

```
[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Keyboard Layout]
"Scancode Map"=hex: 00,00,00,00,00,00,00,00,
                    03,00,00,00,01,00,3a,00,
                    3a,00,01,00,00,00,00,00
```

esc key is: 0x0100

caps key is: 0x3a00

##### Setting up neovim plugins

[NEOVIM: Install and Configure PLUGINS! - YouTube](https://www.youtube.com/watch?v=69tzu7YVlx4)



```bash
mkdir -p .config/nvim/autoload && mkdir -p .config/nvim/vim-plug

```

goto https://raw.githubusercontent.com/junegunn/vim-plug/refs/heads/master/plug.vim and past into

```bash
vim .config/nvim/autoload/plug.vim

```



vim .config/nvim/vim-plug/plugins.vim

```vim
call plug#begin('~/.config/nvim/autoload/plugged')
    Plug 'nvim-treesitter/nvim-treesitter'
    Plug 'kelly-lin/ranger.nvim'
    Plug 'nvim-lua/plenary.nvim'
    Plug 'nvim-telescope/telescope.nvim'
call plug#end()
```



```vim
call plug#begin('~/.config/nvim/autoload/plugged')
    Plug 'preservim/nerdtree'
    Plug 'francoiscabrol/ranger.vim'
    Plug 'liuchengxu/vim-which-key'
    Plug 'nvim-telescope/telescope.nvim'
    Plug 'nvim-lua/plenary.nvim'
    Plug 'rbgrouleff/bclose.vim'
call plug#end()
```



a few plugins to be sorted through:

https://dotfyle.com/plugins/nvim-treesitter/nvim-treesitter

[GitHub - nvim-treesitter/nvim-treesitter: Nvim Treesitter configurations and abstraction layer](https://github.com/nvim-treesitter/nvim-treesitter)

[GitHub - tree-sitter/tree-sitter: An incremental parsing system for programming tools](https://github.com/tree-sitter/tree-sitter)

[Getting Started - Tree-sitter](https://tree-sitter.github.io/tree-sitter/using-parsers/1-getting-started.html)

[GitHub - ranger/ranger: A VIM-inspired filemanager for the console](https://github.com/ranger/ranger)

[GitHub - nvim-telescope/telescope.nvim: Find, Filter, Preview, Pick. All lua, all the time.](https://github.com/nvim-telescope/telescope.nvim)

telescope dependencies...





vim .config/nvim/init.vim

this will be loaded when nvim starts. add this to the file.

```vim
source ~/.config/nvim/vim-plug/plugins.vim
```



ranger requires:

```bash
sudo apt install ranger
```







in vim type command

```vim
:PlugInstall
```



### Keybinds

```vim
vim ~/.config/nvim/keybinds.vim
```

put this in there

```vim
nnoremap <Space>r <cmd>Ranger<cr>
nnoremap <Space>t <cmd>Telescope find_files<cr>
nnoremap <Space>f <cmd>NERDTree<cr>
nnoremap <Space>  <cmd>WhichKey '<Space>' <cr>
```

:Ranger

:Telescope find_files

:NERDTree
