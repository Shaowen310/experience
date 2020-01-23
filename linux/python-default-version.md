# Change python default version

```
sudo update-alternatives --config python
```

Will show you an error:

```
update-alternatives: error: no alternatives for python3
```

You need to update your update-alternatives , then you will be able to set your default python version.

```
sudo update-alternatives --install /usr/bin/python python /usr/bin/python3.4 1
sudo update-alternatives --install /usr/bin/python python /usr/bin/python3.6 2
```

Then run :

```
sudo update-alternatives --config python
```

Set python3.6 as default.

Or use the following command to set python3.6 as default:

```
sudo update-alternatives  --set python /usr/bin/python3.6
```

## References

1. [Stack Exchange: Unix & Linux: Change the Python3 default version in Ubuntu](https://unix.stackexchange.com/questions/410579/change-the-python3-default-version-in-ubuntu)
