# DNS configuration

## Linux

```
systemd-resolve --status
nmcli device show {interface_name} | grep IP4.DNS
```
