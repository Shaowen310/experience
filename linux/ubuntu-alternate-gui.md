# Alternate GUI for Ubuntu Server

It is recommended to keep official GUI for Ubuntu Desktop.

## Lubuntu

### Installation

```
sudo apt install lubuntu-core --no-install-recommends
```

### Boot into test mode & use startx for GUI

First change the run level so the server always boots into command line.

Edit file…

```
/etc/default/grub
```

Change this line to

```
GRUB_CMDLINE_LINUX="text"
```

Make the changes, save the file then update grub with the command…

```
update-grub
```

Set default to multi-user.target
```
sudo systemctl set-default multi-user.target
```

Create the file “.xsession” in the home folder.

```
touch ~/.xsession
```

with containing the text below…

```
lxsession -s Lubuntu -e LXDE
```

Now reboot the server. It should boot into the command line and login.

```
startx
```

will start the Lubuntu desktop environment, already logged in.

Logout will go back to the CLI.

### Essential software

leafpad

## Mate

Genome 2 like

### Installation

```
sudo tasksel install ubuntu-mate-core
```

### Start (from CLI)

```
sudo service lightdm start
```

### Disable (Go back to CLI)

```
sudo systemctl disable lightdm
```

### Purge

```
sudo apt purge -y ubuntu-mate-desktop mate-* ubuntu-mate-* plymouth-theme-ubuntu-mate-* lightdm
sudo apt autoremove -y
sudo shutdown -r now
```

## References

1. [Ubuntu Server with GUI](https://duraturk.wordpress.com/2014/05/12/ubuntu-server-with-gui/)

1. [How to start Ubuntu in Console mode](https://askubuntu.com/questions/859630/how-to-start-ubuntu-in-console-mode/859640)

1. [Ubuntu 18.04: Install MATE for desktop environment](https://www.hiroom2.com/2018/05/06/ubuntu-1804-mate-en/)
