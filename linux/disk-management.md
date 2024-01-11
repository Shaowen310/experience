# Disk Management

## Physical Volume

## Volume Group

### Check

```
sudo vgdisplay
```

### Create

```
sudo vgcreate vg-name /dev/sda1 /dev/sdb1 /dev/sdc1
```

## Logical Volume

### Create

```
sudo lvcreate -L +50G --name datauser ubuntu-vg
```

### Format

```
sudo mkfs -t ext4 /dev/ubuntu-vg/datauser
```

### Rename

```
lvrename /dev/vg02/lvold /dev/vg02/lvnew
lvrename vg02 lvold lvnew
```

### Remove

```
lvremove /dev/testvg/testlv
```

### Add a Filesystem Label

```
e2label /dev/ubuntu-vg/datauser datauser
```

## References

1. [https://opensource.com/business/16/9/linux-users-guide-lvm](https://opensource.com/business/16/9/linux-users-guide-lvm)
2. [https://linuxhint.com/lvm\_home\_directories/](https://linuxhint.com/lvm\_home\_directories/)
