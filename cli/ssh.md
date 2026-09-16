---
tags:
  - cli
  - ssh
  - cli/ssh
  - flags
datum: 2026-09-05
---
> ssh – OpenSSH remote login client

Öffnet eine Remote-Shell oder führt einen Befehl auf einem entfernten Host aus. 
In [[OpenSSH]] werden die generischen Config-Optionen (`-o ...`) beschrieben, welche z.B. auch von [[scp]] verwendet werden.

# Syntax
```shell
ssh [OPTIONEN] USER@HOST [BEFEHL]
```

# Wichtige Flags
- `-p PORT` — Port statt Standard 22
- `-i FILE` — Identity-Datei (Kurzform für `-o IdentityFile=FILE`)
- `-L LPORT:HOST:RPORT` — lokales Port-Forwarding
- `-R RPORT:HOST:LPORT` — remote Port-Forwarding
- `-N` — keinen Remote-Befehl ausführen (nur Tunnel offen halten)
- `-v` — verbose, für Debugging der Verbindung
- `-o`-Optionen (IdentitiesOnly, PreferredAuthentications, …) → [[OpenSSH]]
# Beispiele

```shell
# Verbindung über nicht-Standard-Port
ssh -p 2222 USER@HOST

# Postgres-DB auf dem Server lokal unter Port 5432 erreichbar machen
ssh -L 5432:localhost:5432 USER@HOST

# lokalen Dev-Server (Port 3000) auf dem Server unter Port 8000 erreichbar machen
ssh -R 8000:localhost:3000 USER@HOST

# nur Tunnel zur Postgres-DB offen halten, keine Shell
ssh -N -L 5432:localhost:5432 USER@HOST
```
