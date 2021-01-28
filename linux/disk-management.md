# Disk Management

## Check Volume Group

```text
sudo vgdisplay
```

## Create Logical Volume

```text
sudo lvcreate -L +50G --name datauser ubuntu-vg
```

## Format Logical Volume

```text
sudo mkfs -t ext4 /dev/ubuntu-vg/datauser
```

## Add a Filesystem Label

```text
e2label /dev/ubuntu-vg/datauser datauser
```
