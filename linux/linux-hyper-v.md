# Linux hyper-v guest

## Manual change

Follow these steps to change the screen resolution:

1. From within the Ubuntu virtual machine, open Terminal
1. Type sudo vi /etc/default/grub
1. Find GRUB_CMDLINE_LINUX_DEFAULT="quiet splash"
1. Append that line with video=hyperv_fb:[specify resolution, e.g. 1024x768]
1. Here is what it might look like: GRUB_CMDLINE_LINUX_DEFAULT="quiet splash video=hyperv_fb:1024x768"
1. Save changes and exit
1. Run the following command: sudo update-grub
1. Restart the VM

## References

1. [How To Change the Resolution of an Ubuntu Hyper-V Virtual Machine](https://virtualizationreview.com/blogs/virtual-insider/2014/09/change-ubuntu-resolution-on-hyper-v-vm.aspx)
