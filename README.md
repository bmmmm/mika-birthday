# birthday-card

Minimale, druckbare Geburtstagskarte im Terminal-Look. Läuft komplett im Browser, kein Backend nötig. Alle Inhalte kommen aus URL-Parametern — einfach für andere Personen und Beträge wiederverwendbar.

## URL Parameter

| Parameter | Typ | Default | Beschreibung |
|-----------|-----|---------|-------------|
| `name` | string | `Mika` | Name des Empfängers — erscheint in Überschrift, Nachricht und Meta-Bar |
| `age` | integer | `30` | Alter — steuert Hex/Binary-Anzeige, Stats, Badge und Binärzeile |
| `amount` | float | — | Geschenkbetrag in € — bestimmt Gerät und Laufzeit-Berechnung |
| `meme` | string (URL) | — | Bild-URL für den Meme-Slot (lokal `./meme.jpg` oder remote HTTPS) |
| `from` | string | — | Absendername — erscheint in Meta-Bar und Footer |

Fehlt `amount`, wird kein Gerät berechnet und stattdessen ein Hinweis angezeigt.

## Geräte & Schwellenwerte

Das Gerät wird automatisch gewählt: **höchstes Gerät, das sich mit dem angegebenen Betrag mindestens 30 Tage betreiben lässt** (und dessen Mindestschwelle erfüllt ist).

| Min. Betrag | Gerät | Watt | Beispiel: 75 € → Laufzeit |
|-------------|-------|------|--------------------------|
| 0 € | Kühlschrank (bitcircus101) | 45 W | ~514 Tage |
| 20 € | Router + Switch Stack | 18 W | ~1286 Tage |
| 50 € | Server nutc | 80 W | ~130 Tage |
| 150 € | Lasercutter | 800 W | braucht ≥ 173 € für 30+ Tage |

Strompreis-Basis: **0,30 €/kWh**.

Rechenweg: `Tage = (Betrag / 0,30 €/kWh) / (Watt × 24h / 1000)`

## Meme-Bild einfügen

**Lokale Datei** — Bild neben `index.html` ablegen:
```
?meme=./dein-meme.jpg
```
Funktioniert über einen lokalen Webserver oder GitHub Pages. Nicht über `file://`-URLs (Browser-Sicherheitsregel).

**Remote-URL:**
```
?meme=https://example.com/funny.png
```
Muss HTTPS sein und CORS-Zugriff erlauben. Lädt ohne Serverumweg.

Schlägt das Laden fehl, bleibt der `INSERT MEME HERE`-Platzhalter sichtbar.

## Für andere Geburtstage wiederverwenden

Nur die URL-Parameter ändern — kein Code anfassen:

```
?name=Jonas&age=27&amount=35&meme=./jonas.jpg&from=The+Crew
```

Der `[ copy shareable link ]`-Button baut die URL automatisch aus den aktiven Parametern und kopiert sie in die Zwischenablage.

## Drucken / PDF

Button `[ print / save as PDF ]` oder `Ctrl+P` / `Cmd+P`.

Das Print-CSS schaltet automatisch auf weißen Hintergrund um. In Chrome/Firefox als Drucker „Als PDF speichern" wählen. Buttons und Cursor-Animation werden ausgeblendet.

## GitHub Pages Deployment

Voraussetzung: `gh` CLI installiert und authentifiziert (`gh auth status`).

```bash
# 1. Im Projektordner: Git initialisieren und ersten Commit anlegen
git init
git add index.html README.md
git commit -m "feat: birthday card — generalized"

# 2. Repository erstellen und pushen
gh repo create mika-birthday --public --source=. --push

# 3. GitHub Pages aktivieren (Quelle: main-Branch, Root-Verzeichnis)
gh api repos/$(gh api user --jq .login)/mika-birthday/pages \
  --method POST \
  -f "source[branch]=main" \
  -f "source[path]=/"

# 4. Pages-URL abrufen (kann ~1 Minute dauern)
gh api repos/$(gh api user --jq .login)/mika-birthday/pages --jq .html_url
```

Die Karte ist dann erreichbar unter:
```
https://{dein-username}.github.io/mika-birthday/?name=Mika&amount=50
```

## Beispiel-URLs

```
# Nur Name — kein Betrag, kein Gerät
?name=Mika

# Name + Betrag (Kühlschrank, ~514 Tage bei 45W)
?name=Mika&amount=75

# Mit Meme (lokal) und Absender
?name=Mika&age=30&amount=75&meme=./meme.jpg&from=bitcircus101

# Großzügig — Lasercutter schaltet bei ~173 € frei
?name=Mika&age=30&amount=200&meme=./laser-meme.jpg&from=Anna

# Andere Person, anderes Alter, anderer Absender
?name=Jonas&age=27&amount=35&meme=./jonas.jpg&from=The+Crew

# Vollständig — alle 5 Parameter
?name=Sara&age=33&amount=120&meme=https://example.com/meme.gif&from=Team+Chaos
```
