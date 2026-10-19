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
[source](https://stackoverflow.com/questions/19994922/find-and-replace-strings-in-vim-on-multiple-lines)
```bash
':[range]s/{pattern}/{replacement}/[flags] [count]'

:%s/foo/bar/g  # g for global
```

### consequetive columns of numbers
Start a blockwise select by pressing Ctrl-V. Move the cursor down to select the first column of zeros,
then press g Ctrl-A.
