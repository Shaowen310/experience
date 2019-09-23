# Change hostname

## Ubuntu Server

### Change hostname permanently

Edit /etc/cloud/cloud.cfg and set the parameter "preserve_hostname" from "false" to "true".

Edit hostname

```
hostnamectl set-hostname {new_host_name}
```
