# Linux High-Level Network Stack

## Overview

```
         +----------------------------------+
         |    Application Layer (INET)      |
         +------+--------------------^------+
   User space   |                    |
------------------------------------------------------
  Kernel space  |                    |
         +------v--------------------+------+
         |    Berkeley Socket Interface     |  Interface to users
         +------+--------------------^------+
                |                    |
         +------v--------------------+------+
         |          Protocol Layer          |  TCP/UDP/IP
         +------+--------------------^------+
                |                    |
         +------v--------------------+------+
         | Network Device Driver Interface/ |  Queue for device
         |        Queuing Discipline        |
         +------+--------------------^------+
                |                    |
         +------v--------------------+------+
         |    Physical Device Driver        |
         +------+--------------------^------+
                |                    |
------------------------------------------------------
                |                    |
         +------v--------------------+------+
         |    Physical Device and Media     |
         +----------------------------------+
```

## Sending a packet through socket

Socket

proto_ops

tcp_sendmsg or udp_sendmsg

queue_xmit calls ip_queue_xmit

ip_output.c

Forwarding Information Base (FIB)

The routing information is checked. If packet is fragmented then call ip_fragment function.

ip_route_output_flow

## Receiving a packet from the medium

### Device to driver

1. Driver handles the interrupt issued by device.

1. Driver stores the frame to RAM, allocates sk_buff(skb), and copy the frame to skb

#### sk_buff

It is a doubly linked list.

### Driver to protocol layer

1. Driver puts skb into CPU queue, and issues a "soft" interrupt

1. CPU removes skb from CPU queue, and passes it to network layer. IPv4 `ipv4/ip_iunput.c:ip_rcv()`

1. `ip_input.c:ip_rcv()` calls `ip_rcv_finish()`, and `ip_rcv_finish()` calls `route.c:ip_route_input()`

### Routing

#### ipv4/route.c:ip_route_input()

If destination == me

then calls ip_input.c:ip_local_deliver()

else calls ip_route_input_slow()

#### ipv4/route.c:ip_route_input_slow()

Can forward?

Checks if

* Forwarding enabled?
* Known route?

No: sends ICMP (Destination Unreachable)

### Forwarding a packet

#### Configuration

Packet forwarding is configured for each receiving device

```
/proc/sys/net/ipv4/conf/<device>/forwarding
/proc/sys/net/ipv4/conf/default/forwarding
/proc/sys/net/ipv4/ip_forwarding
```

#### Process

`ipv4/ip_forward.c:ip_forward()`

##### TTL check

if IP TTL > 1

then decreases TTL

else sends ICMP (Time Exceeded)

##### Enqueue priority FIFO (multiqueue)

Priority is based on IP Type of Service (ToS)

* 0 "interactive"
* 1 "best effort" default
* 2 "bulk"

IP ToS: PPPDTRCX

### Sending a packet

`pfifo_fast_dequeue()`

Removes the oldest packet from the highest priority band and passes it to the device driver.

## References

1. [The Journey of a Packet Through the Linux Network Stack](https://www.cs.dartmouth.edu/~sergey/me/netreads/path-of-packet/Lab9_modified.pdf)

1. [PATH OF A PACKET IN THE LINUX KERNEL STACK](https://www.cs.dartmouth.edu/~sergey/netreads/path-of-packet/Network_stack.pdf)
