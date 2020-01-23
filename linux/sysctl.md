# sysctl

## Parameters

variable

The name of a key to read from. An example is kernel.ostype. The '/' separator is also accepted in place of a '.'.

variable=value

To set a key, use the form variable=value, where variable is the key and value is the value to set it to. If the value contains quotes or characters which are parsed by the shell, you may need to enclose the value in double quotes. This requires the -w parameter to use.

-n

Use this option to disable printing of the key name when printing values.

-e

Use this option to ignore errors about unknown keys.

-N

Use this option to only print the names. It may be useful with shells that have programmable completion.

-q

Use this option to not display the values set to stdout.

-w

Use this option when you want to change a sysctl setting.

-p

Load in sysctl settings from the file specified or /etc/sysctl.conf if none given. Specifying - as filename means reading data from standard input.

-a

Display all values currently available.

-A

Same as -a

## Examples

```text
/sbin/sysctl -a
/sbin/sysctl -n kernel.hostname
/sbin/sysctl -w kernel.domainname="example.com"
/sbin/sysctl -p /etc/sysctl.conf
```

## References

1. [sysctl\(8\) - Linux man page](https://linux.die.net/man/8/sysctl)

