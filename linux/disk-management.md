# Disk Management

## Check Volume Group

```text
sudo vgdisplay
```

## Create Logical Volume

```text
sudo lvcreate -L +50G --name datauser ubuntu-vg
```

