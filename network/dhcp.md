# DHCP

## Ubuntu

### Install DHCP server

```
sudo apt install isc-dhcp-server
```

### Configuration

Note: Prior to configurations, need to make sure the targeted interface card is properly setup. May need to assign a static gateway IP to the interface card.

#### 1. Edit the file `/etc/default/isc-dhcp-server`

```
INTERFACESv4="eth0"
```

#### 2. Define your DHCP server options

```
sudo vi /etc/dhcp/dhcpd.conf 
```

Global parameters

```
option domain-name "example.org";
option domain-name-servers ns1.example.org, ns2.example.org;
default-lease-time 3600; 
max-lease-time 7200;
authoritative;
```

Define a subnet

```
subnet 192.168.10.0 netmask 255.255.255.0 {
        option routers                  192.168.10.1;
        option subnet-mask              255.255.255.0;
        option domain-search            "example.org";
        option domain-name-servers      192.168.10.1;
        range   192.168.10.10   192.168.10.100;
        range   192.168.10.110   192.168.10.200;
}
```

[Optional] Configure static IP

```
host centos-node {
	 hardware ethernet 00:f0:m4:6y:89:0g;
	 fixed-address 192.168.10.105;
}

host fedora-node {
	 hardware ethernet 00:4g:8h:13:8h:3a;
	 fixed-address 192.168.10.106;
}
```

#### 3. Start DHCP serivce automatically

```
------------ SystemD ------------ 
$ sudo systemctl start isc-dhcp-server.service
$ sudo systemctl enable isc-dhcp-server.service


------------ SysVinit ------------ 
$ sudo service isc-dhcp-server start
$ sudo service isc-dhcp-server enable
```

#### 4. Allow DHCP service on firewall

```
$ sudo ufw allow  67/udp
$ sudo ufw reload
$ sudo ufw show
```

## References

1. [How to Install a DHCP Server in Ubuntu and Debian](https://www.tecmint.com/install-dhcp-server-in-ubuntu-debian/)
