# Anaconda

## Installation

Miniconda installation guide: [doc](https://docs.conda.io/en/latest/miniconda.html)

## Environment Management

### Create environment

```text
conda create --name myenv python=3.7
```

### List environments

```text
conda info -e
```

### Remove environment

```text
conda remove -n myenv --all
```

### Rename environment \(work around\)

```text
conda create --name new_name --clone old_name
conda remove --name old_name --all
```

### Update environment

```text
conda update --all
```

### Clean cache

```text
conda clean -a
```

### Don't activate base environment automatically

```text
conda config --set auto_activate_base false
```

### Hide environment info

```text
conda config --set changeps1 False
```

## Launching shell with Anaconda environment

### PowerShell

```text
powershell.exe -ExecutionPolicy ByPass -NoExit -Command & 'conda\\shell\\condabin\\conda-hook.ps1' ; conda activate 'conda' ; cd ~ 
```

## Using anaconda with Visual Studio Code

### Numpy DLL not found

Possible reasons:

1. Not launching vscode from anaconda-prompt. Environment variable is not set.
2. Installing numpy using pip. Anaconda environment uses a different installation folder. Should install numpy using command `conda install numpy`.

