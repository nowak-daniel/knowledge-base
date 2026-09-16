---
tags:
  - cli
  - tree
  - list
  - file
  - directory
datum: 2026-07-19
---
> tree - list contents of directories in a tree-like format.

Mit `tree` kann man schnell auf einen Blick die Struktur eines Ordners und seinem Inhalt überblicken.

```shell
# 2 levels deep
tree -L 2

# with all files
tree -a

# with the full path
tree -f

# List directories before files
tree --dirsfirst

# Print the size of each file but in a more human readable way
tree -h

# all together
tree -L 2 -afh --dirsfirst
```
