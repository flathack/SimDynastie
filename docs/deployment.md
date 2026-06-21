# Deployment

SimDynastie wird als fertiges Docker-Image über GitHub Container Registry veröffentlicht.

## Image

```text
ghcr.io/flathack/simdynastie:0.2.0
ghcr.io/flathack/simdynastie:latest
```

## Portainer

1. In Portainer einen neuen Stack anlegen.
2. Inhalt aus [`docker-compose.ghcr.yml`](../docker-compose.ghcr.yml) einfügen.
3. `SIMS2_BACKUP_PATH` auf den Ordner mit den `.tar.gz`-Backups setzen.
4. Stack deployen.
5. App über `http://NAS-IP:7777` öffnen.

## Docker Compose

```bash
cp .env.example .env
docker compose -f docker-compose.ghcr.yml up -d
```

Die App speichert ihre Daten in einem Docker-Volume namens `simdynastie-data`.

## Backup-Ordner

Der Backup-Ordner wird nur lesend eingebunden. Die App importiert die neueste `.tar.gz`-Datei aus diesem Ordner und berücksichtigt aktuell die Nachbarschaft `N004`.

## Updates

```bash
docker compose -f docker-compose.ghcr.yml pull
docker compose -f docker-compose.ghcr.yml up -d
```

Vor Updates empfiehlt sich ein Backup des Docker-Volumes.
