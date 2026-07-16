# SimDynastie

**SimDynastie** ist ein lokales Fan-Tool für große **Die Sims 2**-Stammbäume.
Die App hilft dir dabei, Sims aus einem Savegame übersichtlich zu durchsuchen,
Familienbeziehungen zu verstehen und geplante Hochzeiten zu prüfen.

Der wichtigste Zweck: Du kannst zwei Sims vergleichen und sehen, ob sie
biologisch verwandt sind. Das ist besonders praktisch, weil verwandte Sims in
Die Sims 2 nicht heiraten können.

## Aktueller Stand (öffentlich)

- App-Version: **0.4.2**
- Neueste Image-Referenz: `ghcr.io/flathack/simdynastie:0.4.2`
- Auto-Updater-Manifest: [`latest.json`](latest.json)
- Source-of-Truth: privates Gitea-Repo. Dieses Repo ist die öffentliche
  Release-/Updater-/Deploy-Fassade, kein Code-Mirror.

## Wichtigste Features

- Sims aus einer Die-Sims-2-Nachbarschaft anzeigen
- Stammbäume fokussiert um einen ausgewählten Sim darstellen
- Eltern, Kinder, Geschwister, Großeltern, Cousins und weitere Beziehungen zeigen
- prüfen, ob zwei Sims biologisch verwandt sind
- eine Heiratsliste als Planungshilfe führen
- tote und lebende Sims unterscheiden
- Sim-Portraits anzeigen, sofern sie aus dem Savegame gelesen werden können
- Details im Sim Explorer durchsuchen
- Namenslisten laden ohne sporadische 500-Fehler (v0.4.1 Fix)
- Korrekte Heiratsblockierung: erste Cousins ersten Grades entfernt (`first cousins once removed`) dürfen heiraten (v0.4.2 Fix)

## Schnellstart (Docker)

```bash
# Repo auschecken und Image ziehen
git clone https://github.com/flathack/SimDynastie.git
cd SimDynastie
cp .env.example .env
$EDITOR .env

docker compose -f docker-compose.ghcr.yml pull
docker compose -f docker-compose.ghcr.yml up -d
```

Danach `http://localhost:7777` im Browser öffnen.

## NAS / Dauerbetrieb

Für den Dauerbetrieb auf einem NAS oder Heimserver wird empfohlen, das
neueste GHCR-Image mit einem konkreten Tag zu pinnen (statt `:latest`), damit
versehentliche Redeploys den aktuellen Stand ziehen.

## Auto-Updater (Windows-App)

Falls du die Windows-Variante der App nutzt, ruft der Updater das Manifest
[`latest.json`](latest.json) ab. Die dort hinterlegte `docker_image` zeigt
auf den aktuellen Image-Stand; `windows_x64` und `release_notes` verweisen
auf das letzte veröffentlichte Windows-Release.

## Lizenz

Privates Fan-Projekt. Keine offizielle Veröffentlichung.