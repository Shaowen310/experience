# Operators

## Comparison operators

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

## Logical operators

[Doc](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_logical_operators?view=powershell-7)

| Operator | Description | Example |
| :--- | :--- | :--- |
| `-and` | Logical AND. | `(1 -eq 1) -and (1 -eq 2)` |
|  | TRUE when both statements are TRUE. | `False` |
| `-or` | Logical OR.  | `(1 -eq 1) -or (1 -eq 2)` |
|  | TRUE when either statement is TRUE. | `True` |
| `-xor` | Logical EXCLUSIVE OR.  | `(1 -eq 1) -xor (2 -eq 2)` |
|  | TRUE when only one statement is TRUE | `False` |
| `-not` | Logical not.  | `-not (1 -eq 1)` |
|  | Negates the statement that follows. | `False` |
| `!` | Same as `-not` | `!(1 -eq 1)` |
|  |  | `False` |

### 

