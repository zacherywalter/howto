# tmux.md
nice tutorial [here](https://hamvocke.com/blog/a-quick-and-easy-guide-to-tmux/) and [tmux cheatsheet](https://tmuxcheatsheet.com/)
for :commands first press Ctrl-B the :command

list tmux windows
```bash
tmux ls
```

start new screen with name
```bash
tmux new -s [name]
```

attach to:
-last used session
```bash
tmux a
```

-existing session by name
```bash
tmux a -t [name]
```

# keyboard shortcuts
Detach from session shortcut: Ctrl+B then D (lowercase d)
Switch sessions: Ctrl+B then S (then vim jk for up down)
Switch Window: Ctrl+B then % (split vert) or ; (split horiz)

##### scrolling
enter copy-mode: Ctrl+B then [

# using screen
starting a program in crontab in a screen environment
```bash
@ reboot sleep 15 && sudo screen -S clickScreen sudo click --dpdk -- /home/ubuntu/click/Demonstrator.c    lick
```
If you want to restore screen 10835.pts-0, then type the following command: screen -r 10835
Use the key sequence Ctrl-a + Ctrl-d to detach from the screen session.
Use the key sequence Ctrl-a then esc to go into copy mode, where you can scroll up and down.
