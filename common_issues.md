## Hey there! Here are some quick actions for common issues :)

### Don't like the installation prior to installation of requirements.txt?
Remove the following from **.devcontainer/devcontainer.json**
```
  "postCreateCommand": "pip3 install --user -r requirements.txt"
```
Find it at line 37 (from the original template).

### Don't like the preinstalled formatter?
Remove the following from **.devcontainer/devcontainer.json**
```
        "editor.formatOnSave": true,
        "editor.defaultFormatter": "esbenp.prettier-vscode",
        "[python]": {
          "editor.defaultFormatter": "charliermarsh.ruff",
          "editor.codeActionsOnSave": {
            "source.organizeImports": "always",
            "source.fixAll": "always"
          }
```
Find it at line 8-15 (from the original template).
These are the extensions that formats your code.

and from **.vscode/settings.json**
```
  "editor.formatOnPaste": true
  "editor.formatOnSave": true
```
Find it at line 5-6 (from the original template).
These are the ones that automatically format code the moment you save or paste code in.

### Want to update the default python to a newer python?
Update at **.devcontainer/devcontainer.json**
```
  "image": "mcr.microsoft.com/devcontainers/python:1-3.12-bookworm",
```
Find it at line 3 (from the original template).
This is the 3.12.x python (the latest python) being installed by default.

With your desired python image from:
https://mcr.microsoft.com/en-us/artifact/mar/devcontainers/python/about (recommend as it installs git zsh and curl by default)
https://hub.docker.com/_/python
Or any other site!
