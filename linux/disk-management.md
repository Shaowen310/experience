# Disk Management

## Volume Group

### Check

```text
sudo vgdisplay
```

### Create

```text
sudo vgcreate new_vol_group /dev/sda1 /dev/sdb1 /dev/sdc1
```

## Logical Volume

### Create

```text
sudo lvcreate -L +50G --name datauser ubuntu-vg
```

### Format

```text
sudo mkfs -t ext4 /dev/ubuntu-vg/datauser
```

### Add a Filesystem Label

```text
e2label /dev/ubuntu-vg/datauser datauser
```

## References

1. [https://opensource.com/business/16/9/linux-users-guide-lvm](https://opensource.com/business/16/9/linux-users-guide-lvm)
2. [https://linuxhint.com/lvm\_home\_directories/](https://linuxhint.com/lvm_home_directories/)

