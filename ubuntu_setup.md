# Ubuntu Desktop
[installchromehere](https://www.google.com/chrome/?platform=linux)
```bash
sudo dpkg -i google-chrome-stable_current_amd64
```

##### set power options

##### set background

##### stop sleeping on lid close
```bash
sudo vim /etc/systemd/logind.conf
```
add line 'HandleLidSwitch=ignore'

### openssh-server
[description here](https://www.strongdm.com/blog/enable-ssh-ubuntu)
```bash
sudo apt install openssh-server
sudo systemctl enable --now ssh
sudo systemctl status ssh
sudo ufw allow ssh
sudo ufw enable
```
limit authentication attempts: edit /etc/ssh/sshd_config
uncomment MaxAuthTries 6
PasswordAuthentication no

##### Swap CAPS and ESC
[swap caps and esc](https://medium.com/@ahmaddynugroho/swap-caps-lock-and-escape-in-ubuntu-19-10-and-use-esc-easily-in-vim-vs-code-1d3d68f18764)
```bash
sudo apt install gnome-tweaks
gnome-tweaks
```
keyboard>>Additional Layout Options>>
Caps Lock behavior>>Swap Esc and Caps Lock



