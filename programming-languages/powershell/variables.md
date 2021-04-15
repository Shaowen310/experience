# Variables

## Variable Declaration

```text
$value=0
```

### Notes

1. The line will be executed if a variable is assigned to a command.
2. Variable names are not case sensitive.

### Conventions

1. Variable names are in camelCase

## Variable Usage

### Variable in a string

```text
"$variable"
```

## Environment Variables

### Command line arguments

```text
.\cmd-arg-example1.ps1 FOO
```

cmd-arg-example1.ps1

```text
$param1=$args[0]
```

Concatenate all variables to a string

```text
$s = ""
for ( $i = 0; $i -lt $args.count; $i++ ) {
    $s = -join($s, " ", $args[$i])
} 
```



