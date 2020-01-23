# Linux Kernel Module \(LKM\)

## Makefile

```text
obj-m := hello_1.o
obj-m += hello_2_3.o
  hello_2_3-objs := hello_2.o hello_3.o

all:
  make -C /lib/modules/$(shell uname -r)/build M=$(shell pwd) modules
  rm -r -f *.mod.c .*.cmd *.symvers *.o

clean:
  make -C /lib/modules/$(shell uname -r)/build M=$(shell pwd) clean
```

## Module commands

**depmod** - handle dependency descriptions for loadable kernel modules.

**insmod** - install loadable kernel module.

**lsmod** - list loaded modules.

**modinfo** - display information about a kernel module.

**modprobe** - high level handling of loadable modules.

**rmmod** - unload loadable modules.

## References

1. [Linux kbuild modules](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/tree/Documentation/kbuild/modules.txt)
2. [Linux Kernel Modules - Load, Unload, Configure](http://edoceo.com/howto/kernel-modules)

