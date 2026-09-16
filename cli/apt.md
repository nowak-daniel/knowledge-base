---
tags:
  - cli
  - apt
  - cli/apt
  - update
  - upgrade
  - full-upgrade
  - debian
datum: 2026-07-30
---
> apt provides a high-level commandline interface for the package management system

Die Seite [[systems/apt|apt]] geht weiter auf das System ein und erklärt zum Beispiel wie die history nachvollzogen werden kann.

# `apt upgrade` vs `apt full-upgrade`

`apt upgrade`:
> upgrade is used to install available upgrades of all packages currently installed on the system from the sources configured via sources.list(5). New packages will be installed if required to satisfy dependencies, but existing **packages will never be removed**. If an upgrade for a package requires the removal of an installed package the upgrade for this package isn't performed.

`apt full-upgrade`:
> full-upgrade performs the function of upgrade but will **remove currently installed packages if this is needed** to upgrade the system as a whole.

