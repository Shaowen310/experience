# iptables

## Synopsis

```
iptables [-t table] -[AD] chain rule-specification [options]
iptables [-t table] -I chain [rulenum] rule-specification [options]
iptables [-t table] -R chain rulenum rule-specification [options]
iptables [-t table] -D chain rulenum [options]
iptables [-t table] -[LFZ] [chain] [options]
iptables [-t table] -N chain
iptables [-t table] -X [chain]
iptables [-t table] -P chain target [options]
iptables [-t table] -E old-chain-name new-chain-name 
```

For ipv6 traffic

```
ip6tables [-t table] ...
```

### Basic iptables options

| Option |	Description |
|---|---|
|-A --append 	|Add one or more rules to the end of the selected chain.|
|-C --check 	|Check for a rule matching the specifications in the selected chain.|
|-D --delete 	|Delete one or more rules from the selected chain.|
|-F --flush 	|Delete all the rules one-by-one.|
|-I --insert 	|Insert one or more rules into the selected chain as the given rule number.|
|-L --list 	|Display the rules in the selected chain.|
|-n --numeric 	|Display the IP address or hostname and post number in numeric format.|
|-N --new-chain <name> 	|Create a new user-defined chain.|
|-v --verbose 	|Provide more information when used with the list option.|
|-X --delete-chain <name> 	|Delete the user-defined chain.|
  
### Basic parameters

| Parameter |	Description |
|---|---|
|-p, --protocol 	|The protocol, such as TCP, UDP, etc.|
|-s, --source 	|Can be an address, network name, hostname, etc.|
|-d, --destination 	|An address, hostname, network name, etc.|
|-j, --jump 	|Specifies the target of the rule; i.e. what to do if the packet matches.|
|-g, --goto chain 	|Specifies that the processing will continue in a user-specified chain.|
|-i, --in-interface 	|Names the interface from where packets are received.|
|-o, --out-interface 	|Name of the interface by which a packet is being sent.|
|-f, --fragment 	|The rule will only be applied to the second and subsequent fragments of fragmented packets.|
|-c, --set-counters 	|Enables the admin to initialize the packet and byte counters of a rule.|

### Extensions

Check available kernel modules

```
ls /lib/modules/`uname -r`/kernel/net/netfilter/
```

Check available iptables extensions

```
ls /usr/lib/iptables/
```

## Process Flow

![https://n0where.net/how-does-it-work-iptables](https://d21ic6tdqjqnyw.cloudfront.net/wp-content/uploads/2015/09/08085516/iptables-Flowchart.jpg)

Picture from https://n0where.net/how-does-it-work-iptables

## Delete a rule by index

```
iptables [-t table] -L --line-numbers
iptables -D chain index
```

## Default policies

```
iptables -P INPUT ACCEPT
iptables -P OUTPUT ACCEPT
iptables -P FORWARD ACCEPT
```

## Examples

### NAT services

Remember to enable IP forwarding to let it work.

SNAT

```
sudo iptables -t nat -A POSTROUTING -o eth0 -j SNAT --to-source 1.1.1.1
```

MASQUERADE

```
sudo iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE
```

DNAT

```
sudo iptables -t nat -A PREROUTING -d 10.10.20.99 -j DNAT --to-destination 10.10.14.2
```

#### IP Spoofing (DDoS)

SNAT to attack target's IP

Flood other nodes with ICMP ping messages

#### Port forwarding

DNAT for a single port

```
sudo iptables -t nat -A PREROUTING -p tcp -d 10.10.20.99 --dport 80 -j DNAT --to-destination 10.10.14.2
```

### Firewall

Drop all invalid incoming packets

```
sudo iptables -A INPUT -m conntrack --ctstate INVALID -j DROP
```

### Traffic mirroring

Requires TEE extension.

```
iptables -t mangle -A PREROUTING -d 10.0.3.1 -j TEE --to-destination 192.168.0.1
```

## References

1. [iptables(8) - Linux man page](https://linux.die.net/man/8/iptables)

1. [How do I know if certain iptables extensions are available and enabled?](https://superuser.com/questions/906199/how-do-i-know-if-certain-iptables-extensions-are-available-and-enabled)

1. [Control Network Traffic with iptables](https://www.linode.com/docs/security/firewalls/control-network-traffic-with-iptables/)

1. [How Does It Work: IPTables](https://n0where.net/how-does-it-work-iptables)

1. [How To List and Delete Iptables Firewall Rules](https://www.digitalocean.com/community/tutorials/how-to-list-and-delete-iptables-firewall-rules)

1. [Address Spoofing with iptables in Linux](https://sandilands.info/sgordon/address-spoofing-with-iptables-in-linux)

1. [Mirror all traffic from one port to another on localhost using iptables](https://superuser.com/questions/1289166/mirror-all-traffic-from-one-port-to-another-on-localhost-using-iptables)
