# Variables

## Variable Declaration

```text
$value=0
```

The line will be executed if the variable is assigned to a command.

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

