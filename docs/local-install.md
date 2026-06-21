# Lokale Installation

## Heute verfügbar: Docker

Die stabile lokale Variante ist Docker. Sie läuft auf NAS, Windows mit Docker Desktop, Linux und macOS.

```bash
docker compose -f docker-compose.ghcr.yml up -d
```

Danach:

```text
http://localhost:7777
```

## Möglich: native Desktop-App

Eine lokal installierbare Desktop-App ist technisch möglich. Sinnvoll wäre ein kleines Windows-Installationspaket, das:

- SimDynastie lokal startet
- ein eigenes App-Fenster öffnet
- die Daten lokal speichert
- optional den Backup-Ordner auswählbar macht

Mögliche technische Wege:

- **Tauri oder Wails**: kleines Desktop-Fenster mit lokalem Backend
- **PyInstaller plus WebView**: Python-App mit eingebettetem lokalen Server
- **Docker-freier Windows-Service**: eher für NAS-ähnliche Dauerinstallationen

Für öffentliche Nutzer ist Tauri oder Wails langfristig am angenehmsten. Dafür muss im privaten Entwicklungsrepo ein eigener Desktop-Wrapper gebaut werden. Dieses öffentliche GitHub-Repo bleibt weiterhin nur die Produkt- und Release-Seite.
