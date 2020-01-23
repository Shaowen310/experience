# UFW

## Subnets

When working with UFW, you can also specify IP addresses. For example, if you want to allow connections from a specific IP address, such as a work or home IP address of 203.0.113.4, you need to specify from, then the IP address:

```
sudo ufw allow from 203.0.113.4
```

You can also specify a specific port that the IP address is allowed to connect to by adding to any port followed by the port number. For example, If you want to allow 203.0.113.4 to connect to port 22 (SSH), use this command:

```
sudo ufw allow from 203.0.113.4 to any port 22
```

## Connections to a Specific Network Interface

If you want to create a firewall rule that only applies to a specific network interface, you can do so by specifying “allow in on” followed by the name of the network interface.

If your server has a public network interface called eth0, you could allow HTTP traffic (port 80) to it with this command:

```
sudo ufw allow in on eth0 to any port 80
```

Doing so would allow your server to receive HTTP requests from the public internet.

Or, if you want your MySQL database server (port 3306) to listen for connections on the private network interface eth1, for example, you could use this command:

```
sudo ufw allow in on eth1 to any port 3306
```

This would allow other servers on your private network to connect to your MySQL database.

## References

1. [man utf](http://manpages.ubuntu.com/manpages/bionic/man8/ufw.8.html)
1. [How To Set Up a Firewall with UFW on Ubuntu 18.04](https://www.digitalocean.com/community/tutorials/how-to-set-up-a-firewall-with-ufw-on-ubuntu-18-04)
