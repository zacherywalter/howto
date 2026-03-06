# vim.md
##### by Zachery Walter
- great website for practicing vim navication (here)[https://www.vim-hero.com/]
- extensive cheat sheet (here)[https://vim.rtorr.com/]

### save vim
:w save
:q quit
:q! quit without saving

### change mode

i insert mode before cursor
I insert mode before line

a insert mode after cursor
A insert mode after line

o add line below current line + enter insert mode
O add line above current line + enter insert mode

esc exit current mode

### search

/{term to searh for} then enter
n to goto next entry
N to goto previous entry

### navigation

        up                    k

left          right   h         l
       down                j
       
w jump forwards to the start of a word
b jump backwards to the start of a word

### other

dd delete line
yy (yank) copy a line
p (put) paste
D delete line from cursor to the end
C same as D but enter insert mode
u undo
:redo redo or Ctrl+r

gg go to top of file
G go to bottom of file

### find replace
[source](https://linuxize.com/post/vim-find-replace/#:~:text=In%20Vim%2C%20search%20and%20replace,just%20press%20the%20Esc%20key.&text=range%20%2D%20which%20lines%20to%20apply%20the%20command%20to.)
':[range]s/{pattern}/{replacement}/[flags] [count]'
