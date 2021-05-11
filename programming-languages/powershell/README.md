# PowerShell

## Execute a String as Command

### Invoke-Expression

```text
Invoke-Expression
      [-Command] <String>
      [<CommonParameters>]
```

#### Example

```text
$Command = 'Get-Process | where {$_.cpu -gt 1000}'
Invoke-Expression $Command
```

## Persistent Session

```text
$s = new-PSSession computername
Invoke-Command -session $s { ..script.. }
```

