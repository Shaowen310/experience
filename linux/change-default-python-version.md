# Change default python version

## Use `update-alternatives`

Install configuration

```text
sudo update-alternatives --install /usr/bin/python python /usr/bin/python3 10
```

Then run 

```text
sudo update-alternatives --config python
```

Or use the following command to set python3 as default:

```text
sudo update-alternatives --set python /usr/bin/python3
```

## References

1. Stack Exchange Unix: [Change the Python3 default version in Ubuntu](https://unix.stackexchange.com/questions/410579/change-the-python3-default-version-in-ubuntu)



