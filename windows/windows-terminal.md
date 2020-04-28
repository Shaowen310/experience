# Windows Terminal

## Settings

```javascript
// To view the default settings, hold "alt" while clicking on the "Settings" button.
// For documentation on these settings, see: https://aka.ms/terminal-documentation
{
    "$schema": "https://aka.ms/terminal-profiles-schema",
    "defaultProfile": "{adc1f953-8a62-41e7-a273-42f71f639fdb}",
    "profiles": [
        {
            "guid": "{adc1f953-8a62-41e7-a273-42f71f639fdb}",
            "hidden": false,
            "name": "Anaconda",
            "commandline": "powershell.exe -ExecutionPolicy ByPass -NoExit -Command & 'C:\\Users\\example\\AppData\\Local\\Continuum\\anaconda3\\shell\\condabin\\conda-hook.ps1' ; conda activate 'C:\\Users\\example\\AppData\\Local\\Continuum\\anaconda3'; cd ~ "
        },
        {
            "guid": "{c6eaf9f4-32a7-5fdc-b5cf-066e8a4b1e40}",
            "hidden": false,
            "name": "Ubuntu-18.04",
            "source": "Windows.Terminal.Wsl",
            "colorScheme": "Dracula",
            "fontFace": "Roboto Mono Powerline",
            "fontSize": 11
        }
    ],
    // Add custom color schemes to this array
    "schemes": [
        {
            "name": "Dracula",
            "background": "#282A36",
            "black": "#21222C",
            "blue": "#F1FA8C",
            "brightBlack": "#6272A4",
            "brightBlue": "#D6ACFF",
            "brightCyan": "#A4FFFF",
            "brightGreen": "#69FF94",
            "brightPurple": "#FF92DF",
            "brightRed": "#FF6E6E",
            "brightWhite": "#FFFFFF",
            "brightYellow": "#FFFFA5",
            "cyan": "#8BE9FD",
            "foreground": "#F8F8F2",
            "green": "#50FA7B",
            "purple": "#BD93F9",
            "red": "#FF5555",
            "white": "#F8F8F2",
            "yellow": "#F1FA8C"
        }
    ],
    // Add any keybinding overrides to this array.
    // To unbind a default keybinding, set the command to "unbound"
    "keybindings": []
}
```

### colorScheme

#### Pre-defined color schemes

Campbell, **One Half Dark**, One Half Light, Solarized Dark, Solarized Light

## References

1. [Introducing the Windows Console Colortool](https://devblogs.microsoft.com/commandline/introducing-the-windows-console-colortool/)

