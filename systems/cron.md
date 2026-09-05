---
tags:
  - cron
  - job-scheduling
  - job
  - scheduling
  - notation
datum: 2026-07-19
wikipedia: https://de.wikipedia.org/wiki/Cron
---
# Beschreibung
Der **Cron**-[Daemon](https://de.wikipedia.org/wiki/Daemon "Daemon") dient der zeitbasierten Ausführung von Prozessen in [Unix](https://de.wikipedia.org/wiki/Unix "Unix") und [unixartigen](https://de.wikipedia.org/wiki/Unixoides_System "Unixoides System") [Betriebssystemen](https://de.wikipedia.org/wiki/Betriebssystem "Betriebssystem") wie [Linux](https://de.wikipedia.org/wiki/Linux "Linux"), [BSD](https://de.wikipedia.org/wiki/Berkeley_Software_Distribution "Berkeley Software Distribution") oder [macOS](https://de.wikipedia.org/wiki/MacOS "MacOS"), um wiederkehrende Aufgaben – _Cronjobs_ – zu automatisieren.

Mit dem Befehl [[crontab]] können die Cronjobs verwaltet werden.

# Notation
```
┌───────────── Minute (0 - 59)
│ ┌───────────── Stunde (0 - 23)
│ │ ┌───────────── Tag des Monats (1 - 31)
│ │ │ ┌───────────── Monat (1 - 12)
│ │ │ │ ┌───────────── Wochentag (0 - 6)
│ │ │ │ │
* * * * *  /Pfad/Programmname
```

# [Beispiele](https://de.wikipedia.org/wiki/Cron#Beispiele)

| Minute  | Stunde | Tag des Monats | Monat | Wochentag | Bedeutung                                                                                                                                                                                                                                              |
| ------- | ------ | -------------- | ----- | --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| *       | *      | *              | *     | *         | Jede Minute, rund um die Uhr, sieben Tage die Woche                                                                                                                                                                                                    |
| 0       | 0      | *              | *     | *         | Täglich null Uhr                                                                                                                                                                                                                                       |
| 5       | *      | *              | *     | *         | Fünf Minuten nach jeder vollen Stunde                                                                                                                                                                                                                  |
| */5     | *      | *              | *     | *         | Alle 5 Minuten                                                                                                                                                                                                                                         |
| 1-59/2  | *      | *              | *     | *         | Jede ungerade Minute                                                                                                                                                                                                                                   |
| 5-59/20 | *      | *              | *     | *         | 5, 25 und 45 Minuten nach jeder vollen Stunde                                                                                                                                                                                                          |
| 59      | 23     | *              | *     | 0         | Jeden Sonntag um 23:59 Uhr. Manche Cron-Syntax erlaubt neben 0 für Sonntag auch 7 für Sonntag.                                                                                                                                                         |
| 20,30   | 1      | *              | *     | 1-5       | Montags bis Freitags jeweils um 01:20 und 01:30 Uhr                                                                                                                                                                                                    |
| 0       | 1      | 1-7            | 12    | 1         | Das Programm wird um 1:00 an jedem Tag zwischen 1. und 7. Dezember UND zusätzlich an jedem Montag im Dezember aufgerufen, da hier der Sonderfall greift, dass nur entweder der Tag des Monats oder der Tag der Woche übereinstimmen muss (siehe oben). |
