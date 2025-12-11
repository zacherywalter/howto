# ssh

## install and start ssh server on ubuntu:
sudo apt-get install openssh-server
sudo systemctl enable ssh
sudo systemctl start ssh

check that the server is running:
```bash
sudo systemctl status ssh
```

## using Keys with ssh (rsa):
On the client side create an rsa key pair:
```bash
ssh-keygen -t rsa
```

Copy the public key to the Server:
```bash
ssh-copy-id username@hostname
```

`ssh-copy-id` takes the public key and puts it in
`username@hosname:/home/user/.ssh/authorised`

check permissions:
```bash
chmod 700 ~/.ssh && chmod 600 ~/.ssh/authorized_keys
```
key.pub looks something like:
ssh-rsa and ends with your_username@hostname


Change the ssh standard Port:
sudo nano /etc/ssh/sshd_config
add Port 4444 to file
sudo service ssh restart

## Proxy command:
Jumping to servers over a proxy server

## info:

Some networks are only available over through certain servers on another network.
This makes it necessary to setup paths to help easily access these hidden networks.
As far as I know, The ProxyCommand is only used by SSH connections.

make and open an ssh config file:
sudo vim ~/.ssh/config

add a ProxyCommand on the proxyserver to help make
the stepping stone for jumping to the next server. Example:

```
Host proxy-server
        Hostname proxy-server
        User username
        Port 22
        ProxyCommand ssh username@target-server -W %h:%p
```

proxy-server and target-server are the hostnames thereof.
These can also be defined to fixed IPs in /etc/hosts

sudo vim /etc/hosts

##### Example custom IP Adresses
192.168.8.1     internal-target-server
10.20.2.126     target-server (from the perspective of the proxy-server)

