# Virtual network devices

## Tun/tap

### Allocate a tun/tap device

Note that tun/tap device can only be enabled by attaching an application to it.

```text
sudo ip tuntap add dev tun0 mode {tun|tap}
```

Program interface

Create a new interface or to attach to a persistent interface.

1. Open **/dev/net/tun** file and obtain the file descriptor.
2. Issue an **ioctl\(\)** system call and if it succeeds, the virtual interface is created and the file descriptor we had is now associated to it, and can be used to communicate.

## Bridge

### Allocate a bridge device

```text
sudo ip link add name br0 type bridge
```

### Attach a device to a bridge

Note that tun device cannot be bridged because it does not have MAC address.

```text
sudo ip link set tap0 master br0
```

## References

1. [Tun/Tap interface tutorial](https://backreference.org/2010/03/26/tuntap-interface-tutorial/)

