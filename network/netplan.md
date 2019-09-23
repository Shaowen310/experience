# netplan: Network configuration tool for Ubuntu Server

## Netplan configuration file location

/etc/netplan/50-cloud-init.yaml

## Sample configuration

```
network:
  version: 2
  ethernets:
    ens160:
      dhcp4: false
      addresses: [192.168.0.2/24]
      gateway4: 192.168.0.1
      nameservers:
        search: [example.com]
        addresses: [8.8.8.8]
      optional: true
```

Note that gateway4 assigns the default gateway. The static gateway has higher priority than DHCP assigned gateway.
