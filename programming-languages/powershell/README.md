# PowerShell

## Execute a String as Command

### Invoke-Expression

```
Invoke-Expression
      [-Command] <String>
      [<CommonParameters>]
```

#### Example

```
$Command = 'Get-Process | where {$_.cpu -gt 1000}'
Invoke-Expression $Command
```

## Persistent Session

```
$s = new-PSSession computername
Invoke-Command -session $s { ..script.. }
```
