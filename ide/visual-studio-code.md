# Visual Studio Code

## Variables

[Doc](https://code.visualstudio.com/docs/editor/variables-reference)

## Debug

### StreamLit

```json
{
    "name": "Streamlit run demo.py",
    "type": "python",
    "request": "launch",
    "module": "streamlit",
    "args": [
        "run",
        "demo.py",
    ],
    "cwd":"${workspaceFolder}",
    "console": "integratedTerminal",
    "justMyCode": true
}
```

## Q\&A

### Set working directory

`launch.json`

```
 "cwd": "${workspaceFolder}", # run from workspace folder
 or
 "cwd": "${fileDirname}", # run from the file's folder
```

### Command line argument

```
"args": [
   "--test", "buildOutput/JavaScript1.js",
   "--env", "devtest-chrome-win8"
]
```
