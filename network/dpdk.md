# DPDK

## Compiling a sample app

```
cd examples/helloworld/
export RTE_SDK=$HOME/DPDK
export RTE_TARGET=x86_64-native-linux-gcc

make
    CC main.o
    LD helloworld
    INSTALL-APP helloworld
    INSTALL-MAP helloworld.map

ls build/app
    helloworld helloworld.map
```

## Definitions

**port**: usually refers to ethernet port

**socket**: usually refers to CPU socket

**NUMA node**: NUMA Nodes are CPU/Memory couples. Typically, the CPU Socket and the closest memory banks built a NUMA Node.

## Examples

### l2fwd

1. Use ```--no-mac-updating```

1. Enable promiscuous mode

1. PORTMASK: hexadecimal bitmask of ports to configure

1. All ethernet ports provided by NICs loaded with igb_uio driver are put in a port pool, and PORTMASK indicates the ports to be used.

### l2fwd-crypto

First enque to encryption device, and then deque and l2fwd.

Known issues

1. All encryption devices are set to the same mode which is not desired. One device should work in encryption mode and the other should work in decryption mode.

1. Enthernet header and IP header checksums are not updated after encryption.

1. When in AEAD mode, hash is not discarded after decryption.

1. IV (Initialisation vector) should be set the same for both sender and receiver.

1. ARP messages are dropped.

## References

1. [DPDK Documentation](https://doc.dpdk.org/guides/)

1. [Deploying Intel DPDK in Oracle VirtualBox](https://plvision.eu/rd-lab/blog/networking/deploying-intel-dpdk-in-oracle-virtualbox)

1. [DPDK No Ethernet ports](http://cmdlinelinux.blogspot.com/2018/12/dpdk-no-ethernet-ports.html)

1. [运行testpmd报错Cause: rte_zmalloc(32 struct rte_port) failed](http://sysight.com/index.php?qa=1843&qa_1=%E8%BF%90%E8%A1%8Ctestpmd%E6%8A%A5%E9%94%99cause-rte_zmalloc-32-struct-rte_port-failed)

1. [VMware vSphere — Why checking NUMA Configuration is so important!](https://itnext.io/vmware-vsphere-why-checking-numa-configuration-is-so-important-9764c16a7e73)
