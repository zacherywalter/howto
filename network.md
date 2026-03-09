# networking commands

iwconfig command shows wireless network interfaces
sudo iwlist scan COMMAND shows possible wireless networks?

##### WiFi connection
(here)[https://askubuntu.com/questions/461825/how-to-connect-to-wifi-from-the-command-line]
nmcli -> requires sudo apt install network-manager?
'''bash
sudo nmcli dev wifi	# show available wifi networks 
ip link			# list interfaces 

#disconnect
sudo nmcli d disconnect iface <WifiInterface>

#connect
sudo nmcli d wifi connect <WiFiSSID> password <WiFiPassword> iface <WifiInterface>
'''

##### nmap
'''bash
nmap -Pn <ip>	# list open ports on an ip 
nmap -p 80 example.com
'''

you can ping/nmap with a certain Interface with the -I/-e Attribute

ip neighbour shows neighbors to the computer?
arp -a is same result
`route -n` shows the kernel IP routing table
`ip route` show does something similar i think
(tcp-ip_routing)[https://www.ibm.com/docs/en/aix/7.3.0?topic=protocol-tcpip-routing]
"A route defines a path for sending packets through the Internet network to an address on another network.
Defines a gateway that can forward packets to a specific host on another network.
Defines a gateway that can forward packets to any of the hosts on a specific network."

##### Tunnelling:
https://wiki.linuxfoundation.org/networking/tunneling
https://developers.redhat.com/blog/2019/05/17/an-introduction-to-linux-virtual-interfaces-tunnels#ipip    _tunnel

```bash
ip tunnel del gre0 //delete a tunnel
ip link add name ipip0 type ipip local ... remote ... ttl 64 dev enp5s0
ip link set ipip0 up //start up the previously configured interface/tunnel
```

changing the interface tx queue length: (sudo) # TODO ifconfig is old
ifconfig ${interface} txqueuelen ${size}
ifconfig eth1 txqueuelen 10000
ifconfig eth0 txqueuelen 5000


Networking for Dummies:
http://www.nortonaudio.com/Ficheiros/1118474082.Netwo.pdf
https://edu.anarcho-copy.org/TCP%20IP%20-%20Network/Networking%20For%20Dummies.pdf
https://www.geeksforgeeks.org/computer-network-tutorials/?ref=lbp

ping -I enp5s0 192.168.3.6
sudo ifconfig enp5s0 192.168.3.9 netmask 255.255.255.0
netstat -rn

top cpc 192.168.3.4
bottom cpc 192.168.3.1
3.4 sends arp to 3.1 but 3.1 isn't replying!

see active ssh connections:
netstat --tcp --programs --numeric | grep ssh

see which ports are listening:
sudo netstat -tulpn | grep LISTEN

#TODO test this. Think it's only in gnome?
left alt < takes you to the top of the command history list
left alt >   ----"-----     botom        ----"----

##### set the date
'''bash
sudo date -s "14 Nov 2017 11:57:00"
'''


