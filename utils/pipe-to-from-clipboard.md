# Pipe to/from the clipboard

## Linux

Note that clipboard is provided by X Window System

### xclip

Add alias to `~/.bashrc`

```text
alias xclip="xclip -selection c"
```

Pipe to the clipboard

```text
cat example.c | xclip
```

## Windows

## macOS

## References

1. [Pipe to/from the clipboard in Bash script](https://stackoverflow.com/questions/749544/pipe-to-from-the-clipboard-in-bash-script)

