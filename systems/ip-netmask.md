---
tags:
  - netzmaske
  - subnetzmaske
  - netmask
  - ip
datum: 2026-08-31
---
# Netzmaske
- **Netzmaske / Subnetzmaske**: legt fest, welcher Teil einer IPv4-Adresse das Netz und welcher den Host bezeichnet. Bits auf `1` = Netzanteil, Bits auf `0` = Hostanteil.
- **CIDR-Notation (`/n`)**: gibt die Anzahl der `1`-Bits (Präfixlänge) an, z. B. `/24` = `255.255.255.0`. Löste ab 1993 die klassenbasierte Einteilung (A/B/C) ab.
- **Netzwerkadresse**: erste Adresse im Bereich (Hostanteil = alle `0`), nicht als Host nutzbar.
- **Broadcast-Adresse**: letzte Adresse im Bereich (Hostanteil = alle `1`), nicht als Host nutzbar.
- **Nutzbare Adressen**: `2^(32-Präfix) - 2` (abzüglich Netzwerk- und Broadcast-Adresse).
- **Je kleiner die Präfixlänge, desto größer das Netz** (mehr Hosts, aber weniger Netze möglich) – und umgekehrt.

# [Präfixlängen als Netzgrößen](https://de.wikipedia.org/wiki/Netzmaske#Pr%C3%A4fixl%C3%A4ngen_als_Netzgr%C3%B6%C3%9Fen)

| _Präfix_ | _Netzmaske_       | _Anzahl nutzbarer IPv4-Adressen_                                                                           | _Maske als Bit-Muster_                    |
| -------- | ----------------- | ---------------------------------------------------------------------------------------------------------- | ----------------------------------------- |
| `/0`     | `0.0.0.0`         | `max. 4.294.967.294 (Nur ein großes Netz ohne Router)`                                                     | `0000’0000.0000’0000.0000’0000.0000’0000` |
| `/4`     | `240.0.0.0`       | `max. 268.435.454`                                                                                         | `1111’0000.0000’0000.0000’0000.0000’0000` |
| `/8`     | `255.0.0.0`       | `max. 16.777.214`                                                                                          | `1111’1111.0000’0000.0000’0000.0000’0000` |
| `/12`    | `255.240.0.0`     | `max. 1.048.574`                                                                                           | `1111’1111.1111’0000.0000’0000.0000’0000` |
| `/16`    | `255.255.0.0`     | `max. 65.534`                                                                                              | `1111’1111.1111’1111.0000’0000.0000’0000` |
| `/17`    | `255.255.128.0`   | `max. 32.766`                                                                                              | `1111’1111.1111’1111.1000’0000.0000’0000` |
| `/18`    | `255.255.192.0`   | `max. 16.382`                                                                                              | `1111’1111.1111’1111.1100’0000.0000’0000` |
| `/19`    | `255.255.224.0`   | `max. 8190`                                                                                                | `1111’1111.1111’1111.1110’0000.0000’0000` |
| `/20`    | `255.255.240.0`   | `max. 4094`                                                                                                | `1111’1111.1111’1111.1111’0000.0000’0000` |
| `/21`    | `255.255.248.0`   | `max. 2046`                                                                                                | `1111’1111.1111’1111.1111’1000.0000’0000` |
| `/22`    | `255.255.252.0`   | `max. 1022`                                                                                                | `1111’1111.1111’1111.1111’1100.0000’0000` |
| `/23`    | `255.255.254.0`   | `max. 510`                                                                                                 | `1111’1111.1111’1111.1111’1110.0000’0000` |
| `/24`    | `255.255.255.0`   | `max. 254`                                                                                                 | `1111’1111.1111’1111.1111’1111.0000’0000` |
| `/25`    | `255.255.255.128` | `max. 126`                                                                                                 | `1111’1111.1111’1111.1111’1111.1000’0000` |
| `/26`    | `255.255.255.192` | `max. 62`                                                                                                  | `1111’1111.1111’1111.1111’1111.1100’0000` |
| `/27`    | `255.255.255.224` | `max. 30`                                                                                                  | `1111’1111.1111’1111.1111’1111.1110’0000` |
| `/28`    | `255.255.255.240` | `max. 14`                                                                                                  | `1111’1111.1111’1111.1111’1111.1111’0000` |
| `/29`    | `255.255.255.248` | `max. 6`                                                                                                   | `1111’1111.1111’1111.1111’1111.1111’1000` |
| `/30`    | `255.255.255.252` | `max. 2`                                                                                                   | `1111’1111.1111’1111.1111’1111.1111’1100` |
| `/31`    | `255.255.255.254` | `2 als Punkt-zu-Punkt-Verbindung`                                                                          | `1111’1111.1111’1111.1111’1111.1111’1110` |
| `/32`    | `255.255.255.255` | `genau 1 (Host-Adresse; nicht als Netz nutzbar)`[[1]](https://de.wikipedia.org/wiki/Netzmaske#cite_note-1) | `1111’1111.1111’1111.1111’1111.1111’1111` |