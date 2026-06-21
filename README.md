# SimDynastie

SimDynastie ist eine lokale Web-App für große **The Sims 2**-Stammbäume. Die App importiert ein Savegame-Backup, zeigt Familienbeziehungen in der Nachbarschaft an und hilft dabei zu prüfen, ob zwei Sims biologisch verwandt sind.

Die App läuft ohne Login und speichert Daten lokal in der eigenen Installation.

## Funktionen

- Import von gepackten Sims-2-Backups (`.tar.gz`)
- Anzeige der Nachbarschaft `N004`
- Stammbaum mit Fokus auf einen Sim
- Verwandtschaftsprüfung für zwei Sims
- Heiratsdatenbank als Planungshilfe
- Sim Explorer mit Details, Portraits und Familieninformationen
- Namendatenbank für eigene Vornamen
- Statistikseite zur Nachbarschaft
- Hell-/Dunkelmodus und touch-freundliche Oberfläche

## Docker starten

Voraussetzung: Docker oder Portainer.

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

Danach im Browser öffnen:

```text
http://localhost:7777
```

Für Portainer liegt eine Compose-Datei bei: [`docker-compose.ghcr.yml`](docker-compose.ghcr.yml).

## Lokale Installation

Aktuell ist Docker die empfohlene lokale Installation. Eine native Desktop-App für Windows ist technisch möglich und für eine spätere Version vorgesehen. Sie würde die lokale Web-App starten und in einem eigenen App-Fenster öffnen, ohne dass Nutzer Docker bedienen müssen.

Details: [`docs/local-install.md`](docs/local-install.md)

## Daten und Datenschutz

- Die App ist für lokale Nutzung gedacht.
- Es gibt kein Benutzerkonto und keinen Cloud-Dienst.
- Die importierten Savegame-Daten bleiben in deiner Docker-Installation.
- Die App ist ein Anzeige- und Planungstool. Sie soll Sims-2-Savegames nicht direkt verändern.

## Rechtliches

SimDynastie ist ein unabhängiges Fan-Tool und steht in keiner Verbindung zu Electronic Arts, Maxis oder The Sims. **The Sims 2** und zugehörige Marken gehören ihren jeweiligen Rechteinhabern.

Bitte nutze die App nur mit eigenen Savegame-Backups und erstelle vor jedem Import oder jeder manuellen Arbeit eine Sicherung.

## Version

Aktuelle öffentliche Version: `v0.1.0`

Docker Image:

```text
ghcr.io/flathack/simdynastie:0.1.0
ghcr.io/flathack/simdynastie:latest
```
