# Visual Studio Code

## Variables

[Doc](https://code.visualstudio.com/docs/editor/variables-reference)

## Q&A

### Set working directory

`launch.json`

```text
 "cwd": "${workspaceFolder}", # run from workspace folder
 or
 "cwd": "${fileDirname}", # run from the file's folder
```

### Command line argument

```text
"args": [
   "--test", "buildOutput/JavaScript1.js",
   "--env", "devtest-chrome-win8"
]
```

