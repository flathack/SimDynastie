# Lokale Installation

SimDynastie ist für lokale Nutzung gedacht. Deine Daten bleiben auf deinem
Rechner, deinem NAS oder in deinem Docker-Volume.

## Windows-App

Die bequemste Variante für normale Windows-Nutzer ist die lokale Windows-App.
Sie startet SimDynastie auf deinem Rechner und öffnet die Oberfläche automatisch
im Browser.

[SimDynastie 0.1.0 für Windows herunterladen](https://github.com/flathack/SimDynastie/releases/download/v0.1.0/SimDynastie-0.1.0-windows-x64.zip)

Nach dem Download:

1. ZIP-Datei entpacken.
2. `SimDynastie.exe` starten.
3. Warten, bis sich der Browser öffnet.
4. In der App dein Savegame-Backup importieren.

SHA256:

```text
D8FBA98E5784136B82E2A44AC5A5B377C06F13EBBEA272CA1DE3758FB70C5D61
```

Falls Windows beim ersten Start warnt, prüfe, ob du die Datei aus dem offiziellen
Release heruntergeladen hast.

## Docker

Docker eignet sich für NAS, Portainer, Homeserver oder Nutzer, die SimDynastie
dauerhaft im lokalen Netzwerk laufen lassen möchten.

```bash
docker compose -f docker-compose.ghcr.yml up -d
```

Danach öffnest du:

```text
http://localhost:7777
```

## Welche Variante soll ich nehmen?

- **Windows-App**: empfohlen, wenn du SimDynastie nur auf deinem PC nutzen willst.
- **Docker/NAS**: empfohlen, wenn SimDynastie dauerhaft im Heimnetz laufen soll.

In beiden Varianten bleiben deine Daten lokal.
