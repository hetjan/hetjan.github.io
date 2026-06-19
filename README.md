# Het Jan Marais Fonds – webtuiste

Die amptelike webtuiste van Het Jan Marais Fonds (HJMF). Lewendig by
**https://hetjan.org** (HTTPS word afgedwing), bedien deur GitHub Pages
(repo `hetjan/hetjan.github.io`). Stoot na `main` = publiseer.

## Struktuur

| Lêer / gids | Inhoud |
|---|---|
| `index.html` | Tuisblad |
| `agtergrond.html` | Jannie Marais en die testament |
| `aansoek.html` | Aansoekriglyne en -vorm |
| `terugvoer.html` | Terugvoerverslag-riglyne en -templaat |
| `kontak.html` | Kontakbesonderhede |
| `css/style.css` | Alle stylreëls (`@font-face` en kleur-/lettertipe-veranderlikes heel bo) |
| `assets/` | Logo's (SVG) en favicon |
| `assets/fonts/` | Self-gehuisde lettertipes (Fraunces, Montserrat – woff2) |
| `dokumente/` | Aflaaibare vorms: invulbare PDF-aansoekvorm en Word-terugvoertemplaat |
| `.well-known/security.txt` | Veiligheidskontak (RFC 9116) |
| `CNAME` | `hetjan.org` – **moenie verwyder nie** |

## Om te wysig

Wysig die HTML-lêers direk (teks is gewone Afrikaans tussen die etikette) en
stoor; GitHub Pages publiseer outomaties binne 'n minuut of twee ná elke
stoot na `main`.

- Die kop-navigasie, die voetstuk en die klein inline-`<script>` is in **al
  vyf** bladsye gedupliseer – ’n wysiging aan een van dié blokke moet op
  **al vyf** lêers toegepas word.
- Die jaarlikse datums verskyn op `index.html` (die datumstrook) en
  `aansoek.html` (die intro).

## Sekuriteit en lettertipes

- **Self-gehuisde lettertipes:** Fraunces en Montserrat woon in
  `assets/fonts/` en word via `@font-face` (heel bo in `style.css`) gelaai.
  Die werf maak geen eksterne versoeke nie (geen Google Fonts).
- **E-pos verskans:** `navrae@hetjan.org` verskyn nie as gewone teks in die
  bronkode nie; dit word deur die inline-`<script>` saamgestel (klas
  `js-epos`, met `data-u`/`data-d`), met ’n leesbare terugval
  (`navrae [at] hetjan [dot] org`) wanneer JavaScript af is.
- **Content-Security-Policy:** elke bladsy-kop dra ’n CSP-metaetiket plus
  `referrer`-metaetiket. **LET WEL:** die CSP se `script-src` vaspen ’n
  `sha256`-hutswaarde van die inline-`<script>` se inhoud. As jy daardie skrip
  wysig, **herbereken die hutswaarde en werk die CSP op al vyf bladsye by** –
  anders blokkeer die blaaier die skrip. Hou die skrip ook bis-identies oor al
  vyf bladsye. (Bereken die hutswaarde uit die teks tussen `<script>` en
  `</script>`, UTF-8, SHA-256, base64.)
- `.well-known/security.txt` volg RFC 9116.

## Huisstyl

Diepgroen `#264542` · Room `#F3EFE8` · Brons `#A9854F` · Fraunces (opskrifte en
lopende teks) · Montserrat (klein-kaps etikette). Boonste aanhalingstekens
“…” (nie lae „…” nie). En-strepies –, nooit em-strepies nie. Nie-brekende
spasies in bedrae (`£100 000`). Logo-ontwerp: Nudge Studio (2025).
