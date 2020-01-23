# Packet forwarding

## Routing

### Enable IP forward

Linux

```text
sudo sysctl net.ipv4.ip_forward=1
```

## Bridging

### Enable promiscuous mode

By enabling this, packets with destination MAC address different from the NIC's will not be dropped by the NIC.

This feature requires NIC and its driver's support. For network adapters provided VirtualBox, promiscuous mode should be configured as "Allow All".

Linux

```text
sudo ip link set dev {interface} promisc on
```

## References

1. [Packet forwarding](https://en.wikipedia.org/wiki/Packet_forwarding)

