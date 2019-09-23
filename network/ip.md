# ip

| Object | Abbreviated form | Purpose |
|---|---|---|
| address | a, addr | Protocol (IP or IPv6) address on a device. |
| addrlabel | addrl | Label configuration for protocol address selection. |
| link | l | Network device. |
| maddress | m, maddr | Multicast address. |
| mroute | mr | Multicast routing cache entry. |
| neighbour | n, neigh | ARP or NDISC cache entry. |
| route | r | Routing table entry. |
| rule | ru | Rule in routing policy database. |
| tunnel | t | Tunnel over IP. |
| xfrm | x | Framework for IPsec protocol. |

## Address

### Assign an IP address to an interface

```
ip a add {ip_addr/mask} dev {interface}
```

### Remove an IP address from an interface

```
ip a del {ip_addr} dev {interface}
```

## Route

### Add a new route

```
ip route add default via {gateway_ip} [dev {device}]
ip route add {network/mask} via {gateway_ip} [dev {device}]
ip route add {network/mask} dev {device}
```

### Delete a route

```
ip route del default
ip route del {network/mask} [via {gateway_ip}] dev {device}
```

### Show all routes

```
ip route show table all
```

## Link

### Enable/disable a device

```
ip link set dev {device} {up|down}
```

### Set a NIC in (non-)Promiscuous Mode

Note: Check the device's configuration before running this command. This mode is enabled by default if the device supports promiscuous mode.

```
ip link set dev {device} promisc {on|off}
```

## Multicast address

## Neighbour

### Add an ARP entry

```
ip neigh add {ip_addr} lladdr {mac_addr/ll_addr} dev {device} nud {state}
```

**States**

|nud|description|
|---|---|
|permanent|The neighbour entry is valid forever and can be only be removed administratively|
|noarp|The neighbour entry is valid. No attempts to validate this entry will be made but it can be removed when its lifetime expires.|
|stale|The neighbour entry is valid but suspicious. This option to ip neigh does not change the neighbour state if it was valid and the address is not changed by this command.|
|reachable|The neighbour entry is valid until the reachability timeout expires.|

### Delete an ARP entry

```
ip neigh del {ip_addr} dev {device}
```

## References

1. [Linux ip Command Examples](https://www.cyberciti.biz/faq/linux-ip-command-examples-usage-syntax/)
