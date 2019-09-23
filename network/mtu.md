# MTU

## Introduction

It is the maximum size of a single data unit of digital communications that can be transmitted over a network. The size is fixed for each physical technology. The MTU for Ethernet is 1500 (bytes).

## MTU vs. Maximum TCP Packet Size

The term may be used interchangeably with maximum TCP packet size. It is possible to configure the maximum packet size for protocols such as TCP in OS settings. Low value may cause larger number of packets to be sent while high value may cause fragmentation. Too low or too high value degrades performance.

## Test MTU size

On Windows

```
ping -n 1 -l 1500 -f www.example.com
```

On Linux

```
ping -M do -s 1500 -c 1 www.example.com
```

On macOS

```
ping -D -v -s 1500 -c 1 www.example.com
```

Keep changing the packet size until ping is successful. The MTU size is the successful size plus 28 (IP and ICMP headers size).

## Set MTU size

Linux

```
ip link set dev {device} mtu {mtu_size}
```

## References

1. [Packet Size: Network MTU Vs. Maximum TCP](https://www.lifewire.com/definition-of-mtu-817948)

1. [Ping Test to determine Optimal MTU Size on Router](https://kb.netgear.com/19863/Ping-Test-to-determine-Optimal-MTU-Size-on-Router)

1. [Setting correct MTU for OpenVPN](https://www.sonassi.com/help/troubleshooting/setting-correct-mtu-for-openvpn)

1. [How can I setup the MTU for my network interface?](https://www.cyberciti.biz/faq/how-can-i-setup-the-mtu-for-my-network-interface/)
