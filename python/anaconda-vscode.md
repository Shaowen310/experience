# Using anaconda with Visual Studio Code

## Numpy DLL not found

Possible reasons:

1. Not launching vscode from anaconda-prompt. Environment variable is not set.
1. Installing numpy using pip. Anaconda environment uses a different installation folder. Should install numpy using command `conda install numpy`.
