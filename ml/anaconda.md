# Anaconda

## Create environment

```text
conda create --name myenv python=3.7
```

## Remove environment

```text
conda remove -n myenv --all
```

## Clean cache

```text
conda clean -a
```

## Using anaconda with Visual Studio Code

### Numpy DLL not found

Possible reasons:

1. Not launching vscode from anaconda-prompt. Environment variable is not set.
2. Installing numpy using pip. Anaconda environment uses a different installation folder. Should install numpy using command `conda install numpy`.

