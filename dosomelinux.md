# dosomelinux
Miscellaneous Linux Comands that can sometimes be handy

## Basics
`cat <FILE>` prints out a file in terminal

##### File Permissions
short explanation of setting file permissions (here)[https://gps.uml.edu/tutorials/unix-linux/unix/chmod.htm#:~:text=The%20%22chmod%22%20command%20modifies%20the,search%20permissions%20of%20specified%20directories.&text=%5Bwho%5D%20refers%20to%20who%20you,%3A%20read%2C%20write%20or%20execute.]
```bash
sudo chmod 777 <FILE/DIRECTORY>
```
user=rwx, group=rwx, other=rwx
To see current permissions use.
```bash
ls -l
```
use -a to list hidden files

##### crontab for jobs
config crontab file with:
```bash
crontab -e
```
```bash
sleep 15 && sudo click --dpdk -- /home/ubuntu/click/Demonstrator.click
```

##### keep ubuntu from sleeping
```bash
sudo systemctl mask sleep.target suspend.target hibernate.target hybrid-sleep.target
```
use unmask instead of mask to turn feature back on



##### find the differences in two files with
```bash
grep -Fxvf file1 file2
```
results in everything in file 2 that is not in file 1

(source here)[https://github.com/jgarff/rpi_ws281x]

