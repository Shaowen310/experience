# IP fragmentation and TCP segmentation

## IP fragmentation

1. Maximum Transmission Unit \(MTU\) controls the maximum packet length.
2. IPv4 allows fragmentation during transportation \(by routers\). IPv6 does **NOT** allow fragmentation during transportation.
3. IPv4 only: if router finds MTU of the next hop is smaller than the receiving packet size, it will either drop and send back ICMP or send out the fragmented packets.
4. Unlike TCP segmentation, it will **NOT** tell the sender which fragment is missing.
5. DoS attack

## TCP segmentation

1. Maximum Segment Size \(MSS\) controls the maximum segment length.

## UDP

Its header does not contain data offset info, so it relies on IP fragmentation.

## References

1. [Wiki: IP fragmentation](https://en.wikipedia.org/wiki/IP_fragmentation)

