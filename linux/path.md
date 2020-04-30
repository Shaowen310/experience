# PATH

## Prepend or Append

Prepend

```bash
PATH=~/opt/bin:$PATH
```

Append

```bash
PATH=$PATH:~/opt/bin
```

depending on whether you want to add `~/opt/bin` at the end \(to be searched after all other directories in case there is a program by the same name in multiple directories\) or at the beginning \(to be searched before all other directories\).

## References

1. [Unix Stack Exchange: How to correctly add a path](https://unix.stackexchange.com/questions/26047/how-to-correctly-add-a-path-to-path)

