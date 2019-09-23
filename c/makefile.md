# Makefile

## Options

-C dir

--directory=dir

Change to directory dir before reading the makefiles. If multiple ‘-C’ options are specified, each is interpreted relative to the previous one: ‘-C / -C etc’ is equivalent to ‘-C /etc’. This is typically used with recursive invocations of make (see Recursive Use of make).

## Variables

### Examples

```Makefile
CC=gcc
CFLAGS=-Wall -I.

target: source.c
  $(CC) $(CFLAGS) -o target source.c
```

## Automatic variables

$@ the name of whichever target caused the rule’s recipe to be run

$^ The names of all the prerequisites, with spaces between them.

### Examples

```Makefile
vpn: vpn.c
  gcc -o $@ $^ -g -Wall
```

$@: "vpn"

$^: "vpn.c"

## Life saver

automake or cmake

## References

1. [Automatic-Variables](https://www.gnu.org/software/make/manual/html_node/Automatic-Variables.html)
