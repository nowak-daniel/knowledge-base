---
tags:
  - knowledge-base
  - kb
  - cheatsheet
  - cli
  - tree
  - file
  - walk
  - hierarchy
datum: 2026-07-19
---
> find – walk a file hierarchy

Mit `find` lassen sich schnell bestimmte Ordner oder Dateien finden.

```shell
# find all folder with the name ".venv"
find . -type d -name ".venv"

# find all python files which are not in test folder
find . -type f -name "*.py" -not -path "*/test/*"
```
