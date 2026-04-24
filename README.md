# birthday-card

Nerdy, minimal, printable birthday card generator. Everything driven by URL params.

**→ [bmmmm.github.io/mika-birthday/start.html](https://bmmmm.github.io/mika-birthday/start.html)**  
**→ [github.com/bmmmm/mika-birthday](https://github.com/bmmmm/mika-birthday)**

---

## Pages

| Page | |
|------|-|
| [start.html](https://bmmmm.github.io/mika-birthday/start.html) | Enter a token or go to the builder |
| [builder.html](https://bmmmm.github.io/mika-birthday/builder.html) | Visual editor — live preview, generates token + share link |
| [index.html](https://bmmmm.github.io/mika-birthday/index.html) | The card itself — all params from URL |
| [plain.html](https://bmmmm.github.io/mika-birthday/plain.html) | Plain-text / print version |

---

## URL Params

| Param | Default | Description |
|-------|---------|-------------|
| `name` | `Mika` | Recipient name |
| `age` | `30` | Age — shown in hex/binary, badge, version |
| `amount` | — | Gift in € — selects device + runtime |
| `from` | — | Sender name |
| `theme` | `dark` | Visual theme |
| `quote` | `classic` | Message template ID |
| `text` | — | Custom message (when `quote=custom`) |
| `meme` | — | Image URL or compressed data URL |
| `device` | — | Override device by ID |
| `locked` | — | Hides editor, shows build hint |

---

## Themes

`dark` · `light` · `amber` · `matrix` · `blueprint` · `paper` · `neon` · `dos` · `brutalist` · `ink`

Hidden easter egg: `?theme=uwu`

## Messages

`classic` · `sachlich` · `nerd` · `cli` · `existentiell` · `langweilig` · `birthday_run` · `git_log` · `kernel_panic` · `uptime` · `404`

Custom: `?quote=custom&text=your+message` — supports `{name}` `{age}` `{binary}` `{hex}`

---

## Images / Memes

Three ways to add an image to the card:

**Remote URL** — paste any image URL into `?meme=https://...`. Encoded in the token, works in share links.

**Upload + compress** — pick a local file in the editor. Two options:
- *Print only*: uses a temporary blob URL. Not shareable, not in the token. Good for printing.
- *Compress for link*: resizes to max 400px, JPEG quality 0.35. If the result is under ~150 KB the data URL gets embedded directly in `?meme=data:image/jpeg;base64,...`. Works in share links. Token shows a warning — use the share link instead of the token for image cards.

**Giphy search** — requires a free API key from [developers.giphy.com](https://developers.giphy.com). GIF URL is encoded in the token normally.

---

## Birthday Token

Short typeable code encoding all card params. Generated in the builder, entered on start.html.

Example: `TWlr.YXwz.MHw1.MHx8.Ynxu`

Cards with remote meme URLs produce longer tokens. Cards with embedded (compressed) images should use the share link — the token omits the image in that case.

---

## Devices

Auto-selected: highest device that runs ≥ 30 days on the given amount.

| Device | Watt | Min. € |
|--------|------|--------|
| Kühlschrank (bitcircus101) | 45W | 0 € |
| Router + Switch Stack | 18W | 20 € |
| Server nutc (bitcircus101) | 80W | 50 € |
| Lasercutter (bitcircus101) | 800W | 150 € |

Base: 0.30 €/kWh

---

hacked w/ ♥ by [bitcircus101.de](https://bitcircus101.de)
