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


## dependencies

##### rdepends
Installing .deb packages and their dependencies
sudo apt install apt-rdepends
apt-rdepends <package>|grep -v "^ " 	//lists the dependencies of the package
apt-get download $(apt-rdepends <package>|grep -v "^ " |grep -v "^libc-dev$")

##### install dependencies for pip python
A Similiar thing to rdepends can be done for python-pip packages
If you want to install a bunch of dependencies from, say a requirements.txt, you would do:

mkdir dependencies
pip download -r requirements.txt -d "./dependencies"
tar cvfz dependencies.tar.gz dependencies

And, once you transfer the dependencies.tar.gz to the machine which does not have internet you can
```bash
tar zxvf dependencies.tar.gz
cd dependencies
pip install * -f ./ --no-index
```

