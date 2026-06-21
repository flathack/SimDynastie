# SimDynastie

**SimDynastie** ist ein lokales Fan-Tool für große **Die Sims 2**-Stammbäume.
Die App hilft dir dabei, Sims aus einem Savegame übersichtlich zu durchsuchen,
Familienbeziehungen zu verstehen und geplante Hochzeiten zu prüfen.

Der wichtigste Zweck: Du kannst zwei Sims vergleichen und sehen, ob sie
biologisch verwandt sind. Das ist besonders praktisch, weil verwandte Sims in
Die Sims 2 nicht heiraten können.

## Für wen ist SimDynastie gedacht?

SimDynastie richtet sich an Spielerinnen und Spieler mit großen
Nachbarschaften, Legacy-Spielständen oder langen Familiengeschichten. Wenn dein
Stammbaum irgendwann so groß wird, dass du nicht mehr sicher weißt, wer mit wem
verwandt ist, ist SimDynastie genau dafür gedacht.

Die App läuft lokal. Es gibt kein Benutzerkonto, keine Cloud und keinen
externen Datendienst.

## Was kann die App?

- Sims aus einer Die-Sims-2-Nachbarschaft anzeigen
- Stammbäume fokussiert um einen ausgewählten Sim darstellen
- Eltern, Kinder, Geschwister, Großeltern, Cousins und weitere Beziehungen zeigen
- prüfen, ob zwei Sims biologisch verwandt sind
- eine Heiratsliste als Planungshilfe führen
- tote und lebende Sims unterscheiden
- Sim-Portraits anzeigen, sofern sie aus dem Savegame gelesen werden können
- Details im Sim Explorer durchsuchen
- Namen in einer Namendatenbank sammeln
- Statistiken zur Nachbarschaft anzeigen
- große Stammbäume per Touch, Maus und Scrollen bewegen

Aktuell ist SimDynastie auf die Nachbarschaft `N004` ausgelegt.

## Installation

### Windows-App

Für normale Windows-Nutzer ist eine lokale Windows-App vorgesehen. Sie startet
SimDynastie auf deinem Rechner und öffnet die Oberfläche automatisch im Browser.
Die Daten werden lokal unter deinem Windows-Benutzerprofil gespeichert.

Sobald ein Windows-Paket veröffentlicht ist, findest du es hier:

[Releases öffnen](https://github.com/flathack/SimDynastie/releases)

### Docker oder NAS

Wenn du SimDynastie auf einem NAS, in Portainer oder mit Docker betreiben
möchtest, kannst du das fertige Docker-Image verwenden:

```text
ghcr.io/flathack/simdynastie:0.1.0
```

Mit Docker:

```bash
docker run -d \
  --name simdynastie \
  --restart unless-stopped \
  -p 7777:8000 \
  -e SIMDYNASTIE_DB=/data/simdynastie.sqlite3 \
  -e SIMDYNASTIE_SAVEGAME_ROOTS=/backups \
  -v simdynastie-data:/data \
  -v /pfad/zu/deinen/sims2-backups:/backups/SIMS2:ro \
  ghcr.io/flathack/simdynastie:0.1.0
```

Danach öffnest du:

```text
http://localhost:7777
```

Für Portainer und Docker Compose gibt es eine vorbereitete Datei:

[`docker-compose.ghcr.yml`](docker-compose.ghcr.yml)

Weitere Hinweise findest du in der [Deployment-Anleitung](docs/deployment.md).

## Erste Schritte

1. Starte SimDynastie.
2. Öffne den Bereich **Settings**.
3. Importiere dein Die-Sims-2-Backup oder wähle den vorbereiteten Backup-Ordner.
4. Wechsle zum **Stammbaum**.
5. Suche bei **Sim 1** nach einem Sim.
6. Gib optional bei **Sim 2** einen zweiten Sim ein, um die Verwandtschaft zu prüfen.

Nach dem Import kannst du den Stammbaum ansehen, Sims im Explorer durchsuchen
und geplante Hochzeiten in der Heiratsdatenbank verwalten.

## Wichtige Hinweise

- SimDynastie ist ein Anzeige- und Planungstool.
- Die App soll deine originalen Savegames nicht direkt verändern.
- Arbeite am besten immer mit Savegame-Backups.
- Je nach Savegame können einzelne Daten fehlen oder nicht eindeutig lesbar sein.
- Sehr große Stammbäume werden absichtlich fokussiert angezeigt, damit die App
  bedienbar bleibt.

## Datenschutz

SimDynastie ist für lokale Nutzung gedacht.

- Es gibt kein Benutzerkonto.
- Es gibt keinen Cloud-Sync.
- Deine importierten Savegame-Daten bleiben in deiner lokalen Installation.
- Docker-Installationen speichern ihre Daten im konfigurierten Docker-Volume.
- Die Windows-App speichert ihre Daten lokal in deinem Benutzerprofil.

## Rechtliches

SimDynastie ist ein unabhängiges Fan-Tool und steht in keiner Verbindung zu
Electronic Arts, Maxis oder The Sims. **The Sims**, **Die Sims**, **The Sims 2**,
EA und Maxis sind Marken ihrer jeweiligen Rechteinhaber.

Nutze SimDynastie nur mit eigenen, rechtmäßig genutzten Savegames. Erstelle vor
Importen und Änderungen immer ein Backup. Die Nutzung erfolgt auf eigenes Risiko
und ohne Gewähr.

## Version

Aktuelle öffentliche Version: `v0.1.0`

Docker-Images:

```text
ghcr.io/flathack/simdynastie:0.1.0
ghcr.io/flathack/simdynastie:latest
```

