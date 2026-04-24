# birthday-card

Entstanden für den 30. Geburtstag von Mika — nerdy, minimal, druckbar.  
Jetzt eine generalisierte Vorlage: alle Inhalte kommen aus URL-Parametern, kein Code anfassen nötig. Einfach für jede Person und jeden Anlass wiederverwendbar.

> **Ursprung:** Mika wird 30, wir wollten eine Geburtstagskarte, die zu ihm passt — Hacker-Ästhetik, Stromkostenkalkulation für echte Geräte im bitcircus101, Geburtstagsdaten in Hex und Binary. Jetzt können wir allen die Karte schicken. gg hf wp 🎂

## Schnellstart

**Builder verwenden:** [`/builder.html`](builder.html) — alle Parameter ausfüllen, Theme wählen, Link kopieren.

Oder URL direkt bauen:
```
index.html?name=Mika&age=30&amount=50&from=bitcircus101&theme=dark
```

## URL Parameter

| Parameter | Typ | Default | Beschreibung |
|-----------|-----|---------|-------------|
| `name` | string | `Mika` | Name des Empfängers — Überschrift, Nachricht, Meta-Bar |
| `age` | integer | `30` | Alter — Hex/Binary-Stats, Badge, Binärzeile, Version |
| `amount` | float | — | Geschenkbetrag in € — wählt Gerät + berechnet Laufzeit |
| `meme` | string (URL) | — | Bild-URL für den Meme-Slot (`./lokal.jpg` oder `https://...`) |
| `from` | string | — | Absendername — Meta-Bar und Footer |
| `theme` | string | `dark` | Design-Theme — siehe Tabelle unten |

Fehlt `amount`: Gerät wird nicht berechnet, stattdessen ein Hinweis angezeigt.

## Themes

10 vordefinierte Themes, wählbar via `?theme=NAME` oder im Builder.

| Theme | Look | Display-Font | Mono-Font | Hintergrund |
|-------|------|-------------|-----------|-------------|
| `dark` | Standard-Terminal | Syne 800 | Courier Prime | `#0d0d0d` |
| `light` | Weißes Terminal | Syne 800 | Courier Prime | `#f8f8f6` |
| `amber` | CRT-Monitor orange | Syne 800 | Courier Prime | `#0c0700` |
| `matrix` | Green Terminal | Share Tech Mono | Share Tech Mono | `#000000` |
| `blueprint` | Technische Zeichnung | Syne 800 | IBM Plex Mono | `#001830` |
| `paper` | Gedrucktes Dokument | Playfair Display | Courier Prime | `#f5f0e8` |
| `neon` | Cyberpunk pink | Syne 800 | Courier Prime | `#07000f` |
| `dos` | MS-DOS klassisch | VT323 | VT323 | `#000080` |
| `brutalist` | Hart, roh, schwarz/weiß | Archivo Black | Courier Prime | `#ffffff` |
| `ink` | Warmes Dunkel | Unbounded | Courier Prime | `#1a1410` |

Themes sind modular als JS-Objekte definiert (`THEMES` in `index.html`). Neue Themes hinzufügen:
```js
myTheme: {
  label: 'My Theme',
  vars: {
    '--bg': '#...', '--surface': '#...', '--border': '#...', '--border-dim': '#...',
    '--text': '#...', '--text-dim': '#...', '--text-mid': '#...',
  },
  display: "'Font Name', fallback",
  mono: "'Mono Font', monospace",
},
```

## Geräte & Schwellenwerte

Das Gerät wird automatisch gewählt — **höchstes Gerät, das mit dem Betrag ≥ 30 Tage läuft** und dessen Mindestschwelle erfüllt ist.

| Min. Betrag | Gerät | Watt | Beispiel: 75 € |
|-------------|-------|------|----------------|
| 0 € | Kühlschrank (bitcircus101) | 45 W | ~514 Tage |
| 20 € | Router + Switch Stack | 18 W | ~1286 Tage |
| 50 € | Server nutc (bitcircus101) | 80 W | ~130 Tage |
| 150 € | Lasercutter (bitcircus101) | 800 W | braucht ≥ 173 € für 30+ Tage |

Strompreis-Basis: **0,30 €/kWh**.  
Rechenweg: `Tage = (Betrag / 0.30) / (Watt × 24 / 1000)`

## Meme-Bild

**Klick auf den Meme-Slot** öffnet einen Picker mit drei Tabs:

- **Upload** — lokale Bilddatei (jpg, png, gif, webp), kein Server nötig
- **URL** — direkter Bild-Link (HTTPS, CORS-kompatibel)
- **Search GIFs** — Giphy-Suche mit eigenem API-Key (kostenlos: [developers.giphy.com](https://developers.giphy.com)); Key wird in `sessionStorage` gespeichert

**Via URL-Param:**
```
?meme=./dein-meme.jpg       # lokal, neben index.html ablegen
?meme=https://cdn.example.com/meme.gif   # remote
```

Schlägt das Laden fehl, bleibt der Placeholder sichtbar.

## Für andere Geburtstage wiederverwenden

Einfach Parameter ändern — kein Code anfassen:
```
?name=Jonas&age=27&amount=35&meme=./jonas.jpg&from=The+Crew&theme=blueprint
```

Der **Builder** (`builder.html`) baut die URL automatisch mit Live-Preview der Gerätelaufzeit.

## Shareable Links

`[ copy shareable link ]` baut die URL aus den aktiven URL-Params (keine lokalen Änderungen). Lokale Meme-Uploads fließen nicht in den Share-Link ein — nur `?meme=URL` wird geteilt.

## Drucken / PDF

`[ print / save as PDF ]` oder `Ctrl+P` / `Cmd+P`.  
Print-CSS schaltet automatisch auf weißen Hintergrund. Buttons und Cursor-Animation werden ausgeblendet. In Chrome/Firefox: Drucker „Als PDF speichern" wählen.

## GitHub Pages Deployment

Voraussetzung: `gh` CLI installiert und authentifiziert.

```bash
# Repository erstellen und pushen
git init
git add index.html builder.html README.md
git commit -m "feat: birthday card"
gh repo create mika-birthday --public --source=. --push

# GitHub Pages aktivieren
gh api repos/$(gh api user --jq .login)/mika-birthday/pages \
  --method POST \
  -f "source[branch]=main" \
  -f "source[path]=/"

# URL abrufen (ca. 1 Minute warten)
gh api repos/$(gh api user --jq .login)/mika-birthday/pages --jq .html_url
```

## Beispiel-URLs

```
# Minimal
?name=Mika

# Standard-Karte
?name=Mika&age=30&amount=50&from=bitcircus101

# Mit Meme + Theme
?name=Mika&age=30&amount=75&meme=./meme.jpg&from=bitcircus101&theme=dark

# Neon-Version, Lasercutter
?name=Mika&age=30&amount=200&meme=./laser.jpg&from=Anna&theme=neon

# Andere Person, Blueprint-Theme
?name=Jonas&age=27&amount=35&meme=./jonas.jpg&from=The+Crew&theme=blueprint

# Paper-Theme, kein Meme
?name=Sara&age=33&amount=120&from=Team+Chaos&theme=paper

# DOS-Klassiker
?name=Klaus&age=50&amount=50&theme=dos
```
