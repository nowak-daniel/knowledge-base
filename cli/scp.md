---
tags:
  - cli
  - scp
datum: 2026-09-05
---
> scp – OpenSSH secure file copy

Mit `scp` können Dateien mittels ssh übertragen werden.

# Syntax
```shell
scp source ... target
```

# Wichtige Flags
- `-o`-Optionen (IdentitiesOnly, PreferredAuthentications, …) → [[OpenSSH]]

# Beispiele
```shell
# from local: remote -> local
scp REMOTE_USER@REMOTE_HOST:/PATH/FILE ./ 

# from local: local -> remote
scp ./FILE REMOTE_USER@REMOTE_HOST:/PATH/

# Verzeichnisse (rekursiv)
scp -r ./ORDNER REMOTE_USER@REMOTE_HOST:/PATH/

# Kompression (nützlich bei langsamer Leitung)
scp -C ./FILE REMOTE_USER@REMOTE_HOST:/PATH/
```
