---
tags:
  - OpenSSH
  - ssh
  - scp
  - config
datum: 2026-09-05
---
# OpenSSH

OpenSSH ist die verbreitetste Open-Source-Implementierung des SSH-Protokolls und liefert verschlüsselte Remote-Anmeldung, Befehlsausführung und Dateiübertragung. Auf macOS, Linux und den BSDs ist es der De-facto-Standard.

Folgende CLI-Befehle sind Teil davon bzw. teilen sich dieselbe Client-Konfiguration (`ssh_config`):
- [[ssh]] – Remote-Login / Befehlsausführung
- [[scp]] – Dateikopie über SSH
- [[sftp]] – interaktive Dateiübertragung über SSH
- [[ssh-keygen]] – Schlüssel erzeugen/verwalten
- [[ssh-agent]] / [[ssh-add]] – Agent zum Zwischenspeichern entschlüsselter Keys

Indirekt: `rsync -e ssh` nutzt ssh als Transport und respektiert dieselben `-o`-Optionen, wenn sie über `-e` durchgereicht werden.

## Client
Im folgenden Informationen zu der Konfiguration und Verwendung von dem Client.

### ssh_config

`man 5 ssh_config` beschreibt die Keys die unter `~/.ssh/config` verwendet werden.
### Beispiel: Passwort-Login erzwingen

​```shell
ssh \
  -o IdentitiesOnly=yes \
  -o IdentityFile=/dev/null \
  -o PreferredAuthentications=password \
  USER@HOST
​```

- `IdentitiesOnly=yes` — ssh verwendet nur explizit angegebene Identitäten (IdentityFile/`-i`), statt zusätzlich alle vom ssh-agent angebotenen Keys durchzuprobieren.
- `IdentityFile=/dev/null` — setzt die Identity-Datei auf ein Ziel ohne echten Key, damit gar kein Key-basierter Login-Versuch stattfinden kann.
- `PreferredAuthentications=password` — schränkt die versuchten Auth-Methoden auf `password` ein; publickey, keyboard-interactive, gssapi etc. werden übersprungen.

Zusammen erzwingen die drei Optionen reinen Passwort-Login: ssh probiert weder Agent-Keys noch Identity-Dateien, sondern fragt direkt nach dem Passwort. Nützlich z.B. um zu testen, ob Passwort-Auth auf dem Server überhaupt noch aktiv ist, unabhängig von vorhandenen Keys.

## Server
Im folgenden Informationen zu der Konfiguration auf dem Server.