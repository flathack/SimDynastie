# Lokale Installation

SimDynastie ist für lokale Nutzung gedacht. Deine Daten bleiben auf deinem
Rechner, deinem NAS oder in deinem Docker-Volume.

## Windows-App

Die bequemste Variante für normale Windows-Nutzer ist die lokale Windows-App.
Sie startet SimDynastie auf deinem Rechner und öffnet die Oberfläche automatisch
im Browser.

Sobald ein Windows-Paket veröffentlicht ist, findest du es unter:

```text
https://github.com/flathack/SimDynastie/releases
```

Nach dem Start kannst du in der App dein Savegame-Backup importieren und direkt
mit dem Stammbaum arbeiten.

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
