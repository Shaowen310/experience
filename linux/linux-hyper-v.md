# Linux hyper-v guest

## Screen resolution

Follow these steps to change the screen resolution:

1. From within the Ubuntu virtual machine, open Terminal
1. Type sudo vi /etc/default/grub
1. Find GRUB_CMDLINE_LINUX_DEFAULT="quiet splash"
1. Append that line with video=hyperv_fb:[specify resolution, e.g. 1024x768]
1. Here is what it might look like: GRUB_CMDLINE_LINUX_DEFAULT="quiet splash video=hyperv_fb:1024x768"
1. Save changes and exit
1. Run the following command: sudo update-grub
1. Restart the VM

## Migrate from VirtualBox

1. Create a new VM without disk image.
1. Convert `.vdi` image to `.vhd`image.
1. If encounter failed booting because of video driver, try booting to recovery mode and setting to boot to cmd line by default. Run `startx` to boot to GUI afterwards may fix the problem.

Convert `.vdi` to `.vhd`

![](https://github.com/Shaowen310/experience/blob/master/img/vbox-media-manager.png)

![](https://raw.githubusercontent.com/Shaowen310/experience/master/img/vbox-media-manager-copy-image.png)

## References

1. [How To Change the Resolution of an Ubuntu Hyper-V Virtual Machine](https://virtualizationreview.com/blogs/virtual-insider/2014/09/change-ubuntu-resolution-on-hyper-v-vm.aspx)
