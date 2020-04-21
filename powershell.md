# PowerShell

## Variables

```text
$value=0
```

### Command Line Arguments

```text
.\cmd-arg-example1.ps1 FOO
```

cmd-arg-example1.ps1

```text
$param1=$args[0]
```

## Operators

### Comparison operators

[Doc](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_comparison_operators?view=powershell-7)

| TABLE 1 |  |  |
| :--- | :--- | :--- |
| Type | Operators | Description |
| Equality | -eq | equals |
|  | -ne | not equals |
|  | -gt | greater than |
|  | -ge | greater than or equal |
|  | -lt | less than |
|  | -le | less than or equal |
| Matching | -like | Returns true when string matches wildcard pattern |
|  | -notlike | Returns true when string does not match wildcard pattern |
|  | -match | Returns true when string matches regex pattern; |
|  |  | $matches contains matching strings |
|  | -notmatch | Returns true when string does not match regex pattern; |
|  |  | $matches contains matching strings |
| Containment | -contains | Returns true when reference value contained in a collection |
|  | -notcontains | Returns true when reference value not contained in a collection |
|  | -in | Returns true when test value contained in a collection |
|  | -notin | Returns true when test value not contained in a collection |
| Replacement | -replace | Replaces a string pattern |
| Type | -is | Returns true if both object are the same type |
|  | -isnot | Returns true if the objects are not the same type |

### Logical operators

[Doc](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_logical_operators?view=powershell-7)

| Operator | Description | Example |
| :--- | :--- | :--- |
| `-and` | Logical AND. TRUE when both | `(1 -eq 1) -and (1 -eq 2)` |
|  | statements are TRUE. | `False` |
| `-or` | Logical OR. TRUE when either | `(1 -eq 1) -or (1 -eq 2)` |
|  | statement is TRUE. | `True` |
| `-xor` | Logical EXCLUSIVE OR. TRUE when | `(1 -eq 1) -xor (2 -eq 2)` |
|  | only one statement is TRUE | `False` |
| `-not` | Logical not. Negates the statement | `-not (1 -eq 1)` |
|  | that follows. | `False` |
| `!` | Same as `-not` | `!(1 -eq 1)` |
|  |  | `False` |

### 

## Conditional Statement

### If-else

[Doc](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_if?view=powershell-7)

```text
if (<test1>)
    {<statement list 1>}
[elseif (<test2>)
    {<statement list 2>}]
[else
    {<statement list 3>}]
```

### Switch

[Doc](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_switch?view=powershell-7)

```text
switch [-regex|-wildcard|-exact][-casesensitive] (<value>)
{
    "string"|number|variable|{ expression } { statementlist }
    default { statementlist }
}
```

### 



